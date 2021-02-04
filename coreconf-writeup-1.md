Document Writeup for Working Group Documents

This is a shared writeup for the first two of the four CORECONF drafts:

| name and version                |       date |
|---------------------------------|------------|
| draft-ietf-core-yang-cbor-15    | 2021-01-24 |
| draft-ietf-core-sid-15          | 2021-01-17 |

A second writeup will later be made available for the two other CORECONF drafts:

| name and version                |       date |
|---------------------------------|------------|
| draft-ietf-core-comi-11         | 2021-01-17 |
| draft-ietf-core-yang-library-03 | 2021-01-11 |

> (1) What type of RFC is being requested (BCP, Proposed Standard, Internet Standard, Informational, Experimental, or Historic)? Why is this the proper type of RFC? Is this type of RFC indicated in the title page header?

Both documents are intended for standards-track (Proposed Standard),
as they together with the other two provide the CORECONF
specification, but also can be used individually as interoperability
protocols outside of that shared context.

> (2) The IESG approval announcement includes a Document Announcement Write-Up. Please provide such a Document Announcement Write-Up. Recent examples can be found in the "Action" announcements for approved documents. The approval announcement contains the following sections:

* Technical Summary:

The two drafts provide the foundation to extend YANG-based management
down to constrained devices (RFC 7228).  The parts are:

yang-cbor:
:  encoding rules for serializing YANG using the Concise Binary Object
   Representation (CBOR) [RFC8949], specifically configuration data,
   state data, RPC input and RPC output, action input, action output,
   notifications and yang-data extension defined within YANG modules.

sid:
:  the semantics, the registration, and assignment processes of YANG
   Schema Item iDentifiers (YANG SIDs), globally unique 63-bit
   unsigned integers used to identify YANG items.  To enable these
   processes, also defines a file format used to persist and publish
   assigned YANG SIDs.

The other two drafts, comi and yang-library, apply these drafts by
using the CoAP protocol (RFC 7252) for access and providing
information to be used in conjunction with CoRE resource discovery
(RFC 6690).

* Working Group Summary:

The suite of documents spans specific areas of interest of several
WGs, in particular NETMOD, CBOR, and CORE, as well as NETCONF.
This required coordination between authors and reviewers that see
different of these WGs as their central point of activity.
While the documents were stable already for a while, a specific issue
on representing YANG unions required somewhat unsavory resolutions,
which held up the process considerably.

* Document Quality:

Since the documents became WG documents (in Apr 2016 and Oct 2016),
several reviews were provided by members of the concerned WGs.

Of particular interest are the reviews by Jürgen Schönwälder:
yang-cbor-12: <https://mailarchive.ietf.org/arch/msg/netmod/ls3iMlnJYtRg6NMIAZLGMcSMNpA>
sid: <https://mailarchive.ietf.org/arch/msg/netmod/SMw0cJ_t-NcV6hfDNtf9lYqMp6U>
Jürgen as well as Andy Bierman were very helpful in resolving
remaining issues about these documents as well (Andy also is a
co-author on the comi specification using these two documents).

The SID process is implemented in PYANG modules.
Various parts of the protocol are implemented in proprietary software,
however there is no single go-to implementation that could be
mentioned here.

We are waiting for feedback on the media-types review request,
archived at:
<https://mailarchive.ietf.org/arch/msg/media-types/XMn1cIDryOtRbXdGJUHQCse1tGc>


* Personnel:

Carsten Bormann serves as Document Shepherd.
Barry Leiba is the Responsible Area Director for the CoRE WG.


> (3) Briefly describe the review of this document that was performed by the Document Shepherd. If this version of the document is not ready for publication, please explain why the document is being forwarded to the IESG.

The document shepherd has actively followed the creation of these two
document and has provided a shepherd review that included nits fixed
in the most recent versions.
The document shepherd believes these documents are ready for publication.

> (4) Does the document Shepherd have any concerns about the depth or breadth of the reviews that have been performed?

No.

> (5) Do portions of the document need review from a particular or from broader perspective, e.g., security, operational complexity, AAA, DNS, DHCP, XML, or internationalization? If so, describe the review that took place.

The netconf/netmod perspective was mainly addressed in physical side
meetings at IETFs and in personal reviews.  Briefly, there was traffic
on the mailing list yot@ietf.org, as well, approximately 100 messages
by some 12 individuals.

> (6) Describe any specific concerns or issues that the Document Shepherd has with this document that the Responsible Area Director and/or the IESG should be aware of? For example, perhaps he or she is uncomfortable with certain parts of the document, or has concerns whether there really is a need for it. In any event, if the WG has discussed those issues and has indicated that it still wishes to advance the document, detail those concerns here.

(N/A)

> (7) Has each author confirmed that any and all appropriate IPR disclosures required for full conformance with the provisions of BCP 78 and BCP 79 have already been filed. If not, explain why?

All authors have confirmed that they do not have any direct, personal
knowledge of any patent claim ("IPR") related to each of the drafts
where they are listed as author.

> (8) Has an IPR disclosure been filed that references this document? If so, summarize any WG discussion and conclusion regarding the IPR disclosures.

As of 2021-02-04, no.

> (9) How solid is the WG consensus behind this document? Does it represent the strong concurrence of a few individuals, with others being silent, or does the WG as a whole understand and agree with it?

Many members of the WG don't see YANG as a primary management
interface for their work on constrained devices.  There has been
little opposition against pursuing this as an additional approach
though.  Between the individuals who want to make use of YANG for
constrained devices, there is strong consensus.

> (10) Has anyone threatened an appeal or otherwise indicated extreme discontent? If so, please summarise the areas of conflict in separate email messages to the Responsible Area Director. (It should be in a separate email because this questionnaire is publicly available.)

No.

> (11) Identify any ID nits the Document Shepherd has found in this document. (See http://www.ietf.org/tools/idnits/ and the Internet-Drafts Checklist). Boilerplate checks are not enough; this check needs to be thorough.

ID nits the shepherd found were addressed in the most recent versions.

> (12) Describe how the document meets any required formal review criteria, such as the MIB Doctor, YANG Doctor, media type, and URI type reviews.

The YANG module in sid (a data format specification) does not have warnings.

We are waiting for feedback on the request for media-type review (see above).

> (13) Have all references within this document been identified as either normative or informative?

Yes.

> (14) Are there normative references to documents that are not ready for advancement or are otherwise in an unclear state? If such normative references exist, what is the plan for their completion?

yang-cbor has normative references to RFCs only.
sid has a normative reference to yang-cbor.
(Both have informative references to some of the other CORECONF documents.)

> (15) Are there downward normative references references (see RFC 3967)? If so, list these downward references to support the Area Director in the Last Call procedure.

No.

> (16) Will publication of this document change the status of any existing RFCs? Are those RFCs listed on the title page header, listed in the abstract, and discussed in the introduction? If the RFCs are not listed in the Abstract and Introduction, explain why, and point to the part of the document where the relationship of this document to the other RFCs is discussed. If this information is not in the document, explain why the WG considers it unnecessary.

No.

> (17) Describe the Document Shepherd's review of the IANA considerations section, especially with regard to its consistency with the body of the document. Confirm that all protocol extensions that the document makes are associated with the appropriate reservations in IANA registries. Confirm that any referenced IANA registries have been clearly identified. Confirm that newly created IANA registries include a detailed specification of the initial contents for the registry, that allocations procedures for future registrations are defined, and a reasonable name for the new registry has been suggested (see RFC 8126).

yang-cbor has a relatively plain IANA considerations section, only
adding items to existing registries.
sid has some real innovations in the interactions with IANA, which
were the result of extensive interactions between IANA and the
authors and WG chairs.

> (18) List any new IANA registries that require Expert Review for future allocations. Provide any public guidance that the IESG would find useful in selecting the IANA Experts for these new registries.

sid creates the "YANG SID Mega-Range" registry, the "IETF YANG SID
Range" registry, and the "IETF YANG SID Registry".  All require Expert
Review, both with respect to properly curating a somewhat limited
resource, and with respect to technical soundness of the registrations.

> (19) Describe reviews and automated checks performed by the Document Shepherd to validate sections of the document written in a formal language, such as XML code, BNF rules, MIB definitions, YANG modules, etc.

sid defines a YANG module ietf-sid-file that passes the validation
provided by the datatracker.
yang-cbor contains a single line of ABNF using a production from RFC
Pu7950, which validates with "bap".
yang-cbor also contains many snippets of YANG that have been
eyeball-verified only.

> (20) If the document contains a YANG module, has the module been checked with any of the recommended validation tools (https://trac.ietf.org/trac/ops/wiki/yang-review-tools) for syntax and formatting validation? If there are any resulting errors or warnings, what is the justification for not fixing them at this time? Does the YANG module comply with the Network Management Datastore Architecture (NMDA) as specified in RFC8342?

sid defines a YANG module ietf-sid-file that passes the validation
provided by the datatracker.
This YANG module does not define a datastore, so NMDA does not apply.
