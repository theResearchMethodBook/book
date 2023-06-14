# Guide for Editors 

This is a guide to the process of editing the book. It is intended for the editors of the book. It documents the workflows that are used to manage the book, onto which the editors agreed. 

## Building the Book

### Preparation

#### Clone the book repo with all submodules.

```
git clone --recurse-submodules https://github.com/theResearchMethodBook/book.git
```

Or alternatively

```
git clone https://github.com/theResearchMethodBook/book.git
git submodule init
git submodule update
```

This will fetch all registered chapters to the last registration point of each chapter. This allows chapter authors to work on the chapter without having to worry about the book repo and vice versa. 

#### Pulling updated from the main book repo

If you have already cloned the book repo, you can pull the latest changes from the main book repo with the following command:

```bash
git pull origin main
git submodule update # NEVER use the --remote option at this point!
```

#### Update the book repo with the most recent versions of the chapters

To ensure that no drafts will enter the book, each chapter with changes should be updated selectively. That is one chapter at the time. In order to be strict, **only** update chapters with an open `Chapter update` issue. Close the related issue if the update was successfull **and** the chapter generated no further errors that requires fixing by the authors.

```
git submodule update --remote chapters/THECHAPTERREPONAME
```

Alternatively, one can run the following commands:

```
cd chapters/THECHAPTERREPONAME
git pull origin main
```

Again, THECHAPTERREPONAME needs to be replaced with the name of the chapter repo.

After the update these changes need to be committed and pushed to the book repo.

### Building 

> The editorial process primarily uses the live preview of the book either in RStudio or Visual Studio Code. This section describes the process of building the book manually.

**HTML** The following command will build the html version of the book by default. 

```
quarto render 
```

Alternatively, the following command renders explicitly to HTML: 

```
quarto render --to html
```

**PDF** The following command generates the PDF version: 

```
quarto render --to pdf --toc
```

**ePub** The following command generates the ePub version: 

```
quarto render --to epub --toc
```

## Chapter Proposals

Chapter proposals **must** use the chapter proposal issue template. The template is available as a GitHub issue template.

All editors are notified of new chapter proposals. This only works unless you *unwatch* the book repository, which editors should not do.

Use the comments to discuss the proposal with the authors. 

A chapter proposal that appears to be a duplicate of another chapter or accepted proposal should be labelled as `duplicate` with a comment to the issue of the duplicated proposal. use the hash-tag syntax of GitHub to link to the other issue. This should give the authors the opportunity to clarify significant differences.

## Accepting Chapters

A chapter is accepted by the editors by labelling the chapter proposal as accepted. This is done by adding the label `accepted` to the chapter proposal issue.

- Remove the label `proposed` from the issue.
- Add the label `accepted` to the issue.

Once accepted the chapter issue remains open. The chapter issue is used to track the progress of the chapter.

The editor who accepted the chapter is responsible for creating the chapter repository. This requires the following steps:

- create a new repository in the `theResearchMethodBook` organization.
- select the `chapter-template` as template for the repository. 
- the name of the repo starts with `chapter-` followed by the shortened chapter title in lower case.
- The description of the repo is the full chapter title.
- The repo is created as public repo.
- After creation, the first to lines in `README.md` file are edited. The heading will be the full title of the chapter, the second line will be removed. 
- In the repo settings only issues are enabled. All other features such as Wikis, Projects or Discussions are disabled.
- The submitting author is added to the repo with the role `Maintain`.

## Rejecting Chapters 

A chapter is rejected by the editors by adding the label `rejected` to the chapter proposal issue. 

The issue will be *closed* afterwards with a rejection comment. The comment should explain the reasons for the rejection.

## Reviewing Chapters

> TBD: This section describes the process of following up on the progress of a chapter.

- content review 
- technical review
- copy editing
- reference check

## Publishing Chapters

Once a chapter is ready for publication, it can be added to the main book. This requires two steps: 

1. Link the chapter as submodule into the book repo.
2. Reference the capter in the `_qarto.yaml` file. 

### Linking the Chapter

The chapter is linked as a submodule into the book repo. This is done by adding the chapter repo as a submodule to the `chapters` folder. 

within the book repo do the following: 

```
cd chapters
git submodule add https://github.com/theResearchMethodBook/THECHAPTERREPONAME.git
```

This creates a new folder in the `chapters` folder with the name of the chapter repo, where `THECHAPTERREPONAME` needs to be replaced with the name of the chapter repo. This steps creates a new folder in the `chapters` folder with the name of the chapter repo. 

### Referencing the Chapter

After adding the chapter to the git repository, the chapter needs to be referenced in the `_quarto.yaml` file. This is done by adding the chapter to the `chapters` section of the `_quarto.yaml` file.

The position of the chapter in this list determines the position of the chapter in the book. Reordering the chapters in the list will reorder the chapters in the book and automatically adjust any numbering.

```yaml
chapters:
  - index.qmd
  # ...
  - chapters/THECHAPTERREPONAME/chapter.qmd
  # ...
```
