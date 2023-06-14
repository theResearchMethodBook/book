# Authors' Guide

> This guide assumes that you already have an GitHub account, that you are faminiliar with working with git, and that you have identified the subject of your chapter. 

## The process of a chapter 

### Step 1: Propose a Chapter

Start with choosing a research method and a title. Don't make yout title divert too much from the method, so the readers know what to expect. 

Then, create a new issue in the book repository.

Please read the three checkboxes carefully before checking them.

[create a chapter proposal issue](https://github.com/theResearchMethodBook/book/issues/new?template=chapter-proposal.yaml&title=%5BChapter%5D%3A+%3Ctitle%3E)

### Step 2: Wait for acceptance

The editors will review your proposal and either accept or reject it. 

If it is accepted, a chapter repository is created for you and you will be assigned to it. Your proposal will remain open until the chapter is finished. You find all the details about the required sections, ideas and process in your chapter's `README.md` file.

If rejected, you will be notified and the issue will be closed. 

The editorial team may ask for changes in your proposal using the comments of the issue before the proposal is accepted or rejected. Ensure that you are subscribed to the issue to receive notifications, because otherwiese the issue will be closed after a while of inactivity.

### Step 3: Write your chapter

The editorial teams creates a chapter repository for you. This repository contains a template for your chapter. You can start writing right away. You are able to invite co-authors to your chapter repository.

We have some requirements for your chapter:

1. The chapter abstract must not exceed 350 words.
2. The chapter must not be shorter than 2500 word or exceed 5000 words, without title, abstract, and references.

All communication with the editorial team uses the issues in your chapter repository. 

Please use bibtex for your references and store them in the `references.bib` file. This ensures that all used references are appropriately reported at the end of your chapter.

The Book uses the APA style version 7 for references. We already configured this style for your chapter. Please use the [pandoc citation syntax](https://pandoc.org/chunkedhtml-demo/8.20-citation-syntax.html) throughout your contribution to cite your references in the text. This ensures that you always use the correct reference style.

**Do not** add references manually or add citations below the `## References {-}` header.

### Step 4: Finalise your chapter

When you are done with your chapter, please comment on your chapter proposal. Only after that your chapter will enter the review phase and your chapter will be integrated with the book. 

During this phase you may receive new issues from the editorial team or assigned reviewers that indicate errors or request changes. 

Once your chapter is integrated, the chapter proposal issue will be closed. 

## And Beyond ...

After your chapter is integrated, you may continue working on the chapter in the chapter repository. In order to integrate any changes into the book, you must open an update issue.

When opening an issue the editorial team expects that the changes are already integrated into the chapter repository.

[create an update issue](https://github.com/theResearchMethodBook/book/issues/new?template=chapter-update.yaml&title=%5BChapter%5D%3A+%3Crepo%20name%3E)
