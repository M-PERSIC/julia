# 0001 - Julep Specification and Process

- **Author**: Michael Alexander Persico <michael.a.persico@gmail.com>
- **Created**: 2025-01-10
- **RFC**: [PR link to be added here]()
- **Status**: [Approved]()

```@contents
Pages = ["0001-julep_process_and_guideline.md"]
```

## Abstract

Juleps (Julia Enhancement Proposals) represent a formal process for proposing substantial enhancements to Julia. This proposal formalizes Juleps moving forward and provides a general guideline for submitting a Julep. 

## Rationale

The Julia language continues to evolve since its first stable release. As the language matures, implementing a standard for proposing substantial enhancements would allow for:

- Establishing consensus on enhancements with wide-reaching implications for various stakeholders in the community
- Centralizing discussion for better documenting the context behind each proposal
- Providing a formal roadmap on the direction of the Julia language and ecosystem 

Such a mechanism would be coined "Juleps", previously defined as a term for various written enhancement proposals over the course of Julia's development. This proposal aims to address the need for a more formal proposal process without burdening contributors. Thus, Juleps should be considered optional but highly encouraged for extensive contributions, with fewer restrictions compared to similar processes in other languages. Certain details may be omitted or left intentionally vague, with the understanding that they are either left up to the discretion of the Julia community or will be subject to amendment or inclusion in future revisions of the Julep process.

## Specification

A Julep consists of:

 - A public document with a detailed rationale for the proposal
 - Assets including, but not limited to, code and diagrams 
 - A "requests for comments" (RFC) pull request 
 - A collection of issues and pull requests that together form the documented history of the proposal

The Julep lifecycle is divided into 4 distinct phases. In the RFC phase, an RFC is submitted and discussed by the community before either being rejected or approved. In the implementation phase, development of a concrete implementation of the approved enhancement is ongoing. In the completion phase, the concrete implementation is ready and is submitted for review. In the support phase, the implementation is accepted and a long-term maintenance plan is put into effect, if applicable. 

Specific roles are designated for those involved in the Julep process:

- **Committers** are individuals with commit privileges whom work together to maintain the repositories within the Julia GitHub Organization, as specified in the [Julia Governance Model](https://julialang.org/governance/#julia)
- **Authors** are individuals who share stewardship and specific decision-making authority over a Julep, irrespective of their involvement or contribution level
- **Community members** are individuals within the Julia community that contribute or wish to contribute positively to the Julia language and ecosystem

Committers possess exclusive privileges over the duration of the Julep lifecycle, as they are given sole discretion to:

- Approve or reject a Julep during the RFC phase
- Approve or reject, by vote, the concrete implementation during the completion phase
- Approve or reject modifications to the implementation during the support phase
- Approve or reject, by vote, requests for changes of status
- Schedule triage calls concerning Juleps

Authors possess the exclusive privilege to accept or reject contributions made by committers or community members during the Julep's lifecycle.

Privileges shared between committers and authors include:

- Handling automatic changes of status when certain prerequisites are met

Privileges shared between committers, authors, and community members include:

- Raising issues to be addressed in a triage call
- Request certain changes of status

Committers and community members may contribute towards the concrete implementation of a Julep without becoming authors. Committers and authors still retain their privileges, therefore they must act on behalf of the contributing community members in good faith. The [Julia Stewards Group](https://julialang.org/community/stewards/) must intervene in the event of notable conflict between committers, authors, and/or community members.

The `XXXX-title_here.md` file represents the template file that will serve as the Julep's public document. It is written in Markdown so as to take advantage of [Documenter.jl](https://documenter.juliadocs.org/stable/) and thus leverage the built-in deployment workflow for the Julia repository, as well as allowing for ease of readability of both the render and the source document. The next unassigned number and an appropriate title must be included in the filename in lowercase and with underscores as separators. All rendered Juleps will be published as an online book accessible via the `juleps.julialang.org` URL.

Each public document must include the following elements:

- The title and next unassigned number
- The name and email address of every author (1 or multiple individuals, known as authors, can contribute towards a Julep)
- The date of creation (when the RFC pull request was opened)
- The current status of the Julep
- A table of contents
- An abstract summarizing the proposal in 1 or a few sentences
- A detailed rationale for the proposed enhancement

Additional subsections should be considered for inclusion if they are relevant to the proposal. Custom subsections are permissible for authors to write the Julep public document in their desired structure. Examples include:

- **Specification**: Technical specification, including, but not limited to, specific syntax, semantics, and interface changes. This can be ideal for writing a more concise rationale subsection focused on providing detailed context for the proposal.
- **Backwards Compatibility**: Potential backwards incompatibilities and their severity, as well as how such issues will be addressed. 
- **Security Implications**: Security concerns and their severity, as well as how such issues will be addressed.
- **Reference Implementation**: Code samples that provide a working implementation for the proposal. These can be either part of the public document (recommended) or provided separately.
- **Alternatives**: Discuss rejected ideas, open issues, and additional historical context surrounding the proposal. 

By submitting a Julep, all authors agree to license the public document and any included non-code assets under the [Creative Commons Attribution 4.0 International
license](https://creativecommons.org/licenses/by/4.0/). If code is provided separately from the public document, then the following rules must be respected unless the authors can provide sufficient justification in their RFC pull request:

- All code not included in the public document must form part of 1 or several Julia packages
- All code must be included alongside the public document in the repository
- All authors agree to license their code under the [MIT License](https://spdx.org/licenses/MIT.html)
- A working [Manifest.toml](https://pkgdocs.julialang.org/v1/toml-files/#Manifest.toml) file for every package must be included
- Compat entries must be strictly set to [exact versions](https://pkgdocs.julialang.org/v1/compatibility/#Equality-specifier) for both Julia and all dependencies

It is possible to handle multiple votes and issues relating to multiple Juleps in a single triage call, however every point of discussion must be clearly defined when the triage call is announced. A triage call must be scheduled if a change of status requires a vote or if committers, authors, or community members wish to address any topics concerning their Julep that cannot be addressed in an alternative manner. In the latter instance, an issue must be filed by the original committers, authors, or community members and at least 2 disinterested committers must approve the request. A triage call must be scheduled no later than 30 days inclusively following a request, with reasonable extensions allowed for holidays, scheduling conflicts, or exceptional circumstances. Committers, authors, community members may join the call. Any point of discussion during the triage call must be discussed in a thorough and transparent manner, and input from committers, authors, and community members must be taken into account before proceeding with votes. Every vote requires a 70% supermajority of committers for approval, and the vote is considered valid only if conducted during the call. A detailed summary of the call must be attached to all issues and pull requests that are the subject of the call. The triage call may be conducted either via video call, in-person meeting, or online chat, with appropriate accommodations made for all attendees irrespective of location.

Each Julep has an associated status detailing its current phase in its lifecycle. Committers, authors, or community members may submit requests for changes of status depending on which status is being requested. A Julep may be considered:

- **Approved**: Julep has completed its RFC phase and has been accepted. Specifically, the RFC pull request for the Julep has been approved and merged. A change of status to Approved requires a vote on merging the RFC pull request during a triage call. A link must be included to the merged RFC pull request in the public document.
- **In Progress**: Julep is in the implementation phase and the implementation pull request has been opened. Approval for a change of status to In Progress is automatic once the implementation pull request is opened. A link must be included in the public document to the open implementation pull request.
- **Active**: Julep has been successfully implemented, meaning the proposed enhancements have been approved and merged. Minor corrections and amendments may be performed over time that do not require a separate Julep to be submitted. A change of status to Active requires a vote on merging the implementation pull request during a triage call. A link must be included in the public document to the merged implementation pull request.
- **Superseded**: A new Julep significantly amends or supplants the current Julep. Approval for change of status to Superseded is automatic once the RFC pull request for the other Julep is accepted and merged. A link must be included in the public document to the merged RFC pull request of the superseding Julep.
- **Withdrawn**: Julep has been voluntarily withdrawn by the authors. All authors need to approve the request for a change of status to Withdrawn. Following an approved change of status, all pull requests and issues by the authors concerning the Julep must be closed. A request for change of status to Withdrawn requires the approval of all authors and at least 1 committer. It is strongly advised that a triage call be scheduled in order to discuss the potential implications for the Julia language and ecosystem. A link must be included in the public document to the issue requesting the change of status.
- **Rejected**: Julep has been rejected. Careful consideration must be made to resolve any concerns during the RFC phase in order to avoid rejection during the implementation phase. A Rejected status is different from rejecting a Julep during the RFC phase: in that instance the Julep is not considered to have existed, thus the RFC pull request is simply closed. A change of status to Rejected requires a vote during a triage call. A link must be included in the public document to the issue requesting the change of status.
- **Inactive**: No activity by any of the authors for a period of exactly 6 months. Lack of activity is defined as all authors not replying to any correspondence from community members, along with a lack of an explanation for no correspondence, and no activity within the Julia community during that period. After exactly 6 months, the authors must be reached out via their provided contact information to warn them that their Julep risks becoming inactive. Following exactly 12 months of inactivity, the change of status to Inactive is automatic. If other individuals wish to become authors and pursue implementation, they must file a new Julep that will supersede the inactive Julep. No request can be made for a change of status to Inactive. A link must be included in the public document to the pull request implementing the change of status.
- **Frozen**: The authors have signalled that they are unable to pursue development of the Julep. A change of status to Frozen can be requested by the authors at any point following the RFC phase and before the support phase. Not all authors need to signal this change of status if they are unavailable for justifiable reasons or cannot be reached. If other individuals wish to become authors and pursue implementation, they must first gain the approval of all active authors. The individuals must also prepare a new open implementation pull request. They must then submit a separate pull request, co-authored by all active original authors, to add themselves to the Julep public document and request a change of status to In Progress. A request for change of status to Frozen requires the approval of all active authors and at least 1 committer. It is strongly advised that a triage call be scheduled in order to discuss the potential implications for the Julia language and ecosystem. A link must be included in the public document to the issue requesting the change of status.
- **Retired**: Julep is considered obsolete. A change of status to Retired requires a vote during a triage call. A link must be included in the public document to the issue requesting the change of status.

|    **Status**   |                         **Status Relationship**                         |               **Request**              |             **Change Prerequisite**            |         **Approval Method**        |
|:---------------:|:-----------------------------------------------------------------------:|:--------------------------------------:|:----------------------------------------------:|:----------------------------------:|
|   **Approved**  | In Progress, Superseded, Withdrawn, Rejected, Inactive, Frozen, Retired |                 Authors                |              Open RFC pull request             |          Vote before merge         |
| **In Progress** |    Active, Superseded, Withdrawn, Rejected, Inactive, Frozen, Retired   |                 Authors                |        Open implementation pull request        |              Automatic             |
|    **Active**   |                           Superseded, Retired                           |                 Authors                |        Open implementation pull request        |          Vote before merge         |
|  **Superseded** |                                    -                                    | Committers, Authors, Community Members | Merged RFC pull request from superseding Julep |              Automatic             |
|  **Withdrawn**  |                                    -                                    |                 Authors                |                  Issue opened                  |     All authors and 1 committer    |
|   **Rejected**  |                                    -                                    |      Committers, Community Members     |                  Issue opened                  |                Vote                |
|   **Inactive**  |                       In Progress, Frozen, Retired                      |                    -                   |             12 months of inactivity            |              Automatic             |
|    **Frozen**   |          In Progress, Superseded, Withdrawn, Rejected, Retired          |                 Authors                |                  Issue opened                  | All active authors and 1 committer |
|   **Retired**   |                                    -                                    | Committers, Authors, Community Members |                  Issue opened                  |                Vote                |

## Workflow

It is first advised to discuss potential enhancements with others in the Julia community in order to gain initial feedback. Community members can be reached out to via Julia's various [Community Channels](https://julialang.org/community/#community_channels) and [GitHub Organizations](https://julialang.org/community/organizations/#julia_github_organizations).

A proposed enhancement should be considered "substantial" in order for a Julep to be considered. A "substantial" enhancement is generally defined as any change that will contribute a net benefit to Julia by introducing or significantly modifying: 

- Language features (syntax, semantics, interfaces)
- Core components (standard library)
- Project infrastructure (CI/CD, documentation, licensing) 

Examples of enhancements that are not substantial may include:
- Bux fixes
- Minor documentation corrections or improvements
- "Local" performance improvements (those that affect specific contexts)
- Changes that will go unnoticed by a significant majority of Julia users  

Note that these criteria are both intentionally ambiguous and non-exhaustive, and are meant to provide a general understanding for when a Julep is necessary. It is important to think of a Julep as a public point of discussion on extensive contributions to the Julia language and ecosystem.  

All concerns raised throughout the Julep's lifecycle must be addressed by the Julep authors on a best effort basis. Certain criteria for evaluating whether the proposed enhancements will be accepted include, but are not limited to:

- The quality of the contribution 
- Technical concerns related to performance, security, interoperability, and other factors
- Strategic alignment with the direction of the Julia language and ecosystem
- Maintainability during the support phase 
- Extensive testing and documentation

Once the proposed enhancements have been discussed, place a copy of the template directory, with matching filename and directory name, under the `juleps` directory. If applicable, create a proof-of-concept implementation alongside the Julep public document. A working demonstration of the proposed enhancements will provide a more effective method for consensus building over the course of the RFC phase, as well as identify any potential issues.

Each author is formally recognized by including their name and email address in both the public document and by having them co-author the RFC pull request like so:

```md
Co-authored-by: Jane Doe <jane.doe@gmail.com>
Co-authored-by: John Smith <john.smith@outlook.com>
```

Every author possesses equal contribution rights, meaning that each of them have full privileges to modify status, implement changes, and maintain shared authorship of the Julep. Only 1 author need be active over the duration of the entire Julep lifecycle. A Julia GitHub Organization can officially endorse a Julep by having a recognized member become an author.

An author may request at any time before the support phase to relinquish authorship before the support phase. This is performed by submitting a pull request that must include justification in the description and which scrubs their name from the Julep public document.

Once the Julep has been drafted, all authors must agree to submit an RFC pull request to the Julia repository. Any issue or pull request relating to a Julep must include `[Julep]` in the beginning of the title as well as its assigned number, with the exception of the RFC pull request. The RFC pull request must specifically include `[Julep] RFC: ` and the title stated in the public document, and the pull request description must include:

- The abstract from the public document
- An abridged rationale for the Julep
- All co-authors

If the Julep is approved, then the RFC pull request must be merged. The Julep number may need to be changed before merging if other Juleps have been approved during the RFC phase. A render is produced and incorporated into the Julep book. The implementation phase begins and it is expected that an implementation pull request will be opened.  

It is advised that the implementation pull request be kept as a draft so as to document its development and allow community members to take part in its development through feedback. Once the concrete implementation is ready, open the implementation pull request to signal to committers the change of status request to Active. This will be an involved phase of the Julep process, as all parties involved will continuously work together to ensure that the implementation adheres to quality standards. It is strongly advised to consult the Julia manual for [performance tips](https://docs.julialang.org/en/v1/manual/performance-tips/), [code styling](https://docs.julialang.org/en/v1/manual/style-guide/), and other important aspects that contribute towards a quality enhancement of the Julia language.

If the concrete implementation is approved and the status is changed to Active, then the support phase begins and authors must provide continued maintenance of their enhancements. The Julep process is now considered complete and no further formalities are expected on the part of the authors with the exception of respecting role privileges. The public document may be modified over time, with the approval of at least one committer, for minor corrections and amendments that do not significantly alter the original proposal. 
