> DARE UK Federated Architecture Blueprint  v2.2
----

# Chapter 5 Federated architecture: data layer
## Data reusability

Reusability in a sensitive data environment has to be balanced against governance principles which restrict use of data to pre-approved purposes only. We can draw two broad categories of reusability:
 1. Reuse under original approvals. Assembled datasets and analyses derived from them (including computer programs) may result in a model for which evidence must be preserved for many years (for example clinical trials or medical devices). The datasets and analyses must be preserved in a way that could be checked and re-validated in the future, but all within the same purpose for which approvals were originally granted (and all within the same, or an equivalent, TRE). This then becomes the challenge of preserving long-term a digital object that is quite possibly encrypted. Specialised archive services could be developed that would do this (many already exist).
 2. Reuse for new research. Whether a new research project—perhaps under a new team, perhaps linking in additional data—could be authorised to build on the full results of another is clearly a governance question. (By “full results” we mean the full linked data and analysis environment that remains within the TRE, not the summary results approved for egress.)

In technical terms, a service which preserved the TRE environment for the purposes in (1) would serve equally to support those in (2). We do not expand on the details of such a service here.

