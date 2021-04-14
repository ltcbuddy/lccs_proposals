# Litecoin Community Crowdfunding System (LCCS)

static site currently viewable at: https://ltcbuddy.github.io/lccs_site/

https://github.com/ltcbuddy/lccs_proposals

This repository contains the content and history of proposals as they work through the crowdfunding lifecycle, and acts as a collaboration spot that facilitates the discovery, discussion, and vetting of proposals.

As each proposal works through the lifecycle, its status is updated within the proposal document's front matter (a technical term borrowed from the technology used to process the proposal documents into a static website). The layout attribute is updated to equal the respective lifecycle state: vetting, funding, working, or complete.

Workflow

First, the Proposer creates a proposal for work to be funded and then submits the proposal as a pull request to this proposals repository. These proposals are in the vetting state.

Until the proposal in the pull request is accepted by the community and/or LTC Foundation and merged into this repo, it is not considered to be in the funding state. As a part of the acceptance process validation of the proposal's format, including front matter and file name, should be performmed by reviewers. As a final part of the vetting/acceptance process, a funding address is created, assigned, and edited into the proposal's front matter before being merged. Once the proposal is finalized and accepted by the community and/or LTC Foundation it gets merged and enters the funding state.

Once the proposal becomes fully funded, the proposal document is updated to be in the working state.

Finally, once the proposal's tasks have been worked and paid, the status (the layout attribute -- which is a tight coupling to jekyll, but, it's a quick hack that works) is updated to be complete.

The Implementation of LCCS uses GitHub actions to process pull request and merge related events (and can be triggered manually too by the repository owners). This processing also validates that the PR title matches an expected format since automated processing in the site repo consumes PR titles before being accepted. Any merge into this repo triggers an update of the static site repo, including the content in the proposals submodule. This is how the proposals in the vetting state become known to the static content site.

https://github.com/ltcbuddy/lccs_site

This repository contains the content and source code of a jekyll generated static web site that makes it easy for people to view the active proposals in each stage of the lifecycle.

The Implementation of LCCS uses GitHub Pages for ease of hosting. A todo item is to configure and use a custom domain name instead of using the github.io URL (this is easily configured with the CNAME file).
