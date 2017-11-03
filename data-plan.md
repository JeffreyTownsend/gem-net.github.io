---
layout: misc
title: Data Plan
permalink: /data-plan/
---


# Data Management and Communication Plan


The following plan is a preliminary suggested workflow for managing, tracking, and discussing sequences across C-GEM during Phase I. The plan, which will evolve based on feedback from C-GEM collaborators, aims to satisfy the following requirements and specifications:

1. a secure, centralized, easy-to-access sequence repository;
2. search functionality across sequences;
3. centralized, searchable communication at two scales: high level project discussion and individual sequence discussion;
4. as few tools as possible, and as simple and intuitive as possible, to maximize ease of adoption;
5. each tool should have a clearly defined purpose, so it's obvious when to use each tool;
6. minimal effort required to keep information up-to-date;
7. ability to share short status updates on lab progress;
8. at-a-glance information on project status and number of sequences shared;
9. users should get a manageable and customizable number of notifications relevant to them;
10. labs have complete control over what data they share with C-GEM collaborators, and shared sequence objects can be read-only;
11. new C-GEM researchers should have immediate access to all data, and access can be discontinued for departing researchers.

The three pieces of software in this plan are **Benchling** (for sequence storage, annotation, and search), **Asana** (for sequence-level discussion, with links to Benchling), and **Slack** (for project-level discussion).


## Benchling: the C-GEM sequence inventory

![Benchling demo](/img/data-plan/benchling_inventory.jpg)
*A screenshot showing the first two sequences in the GEM-NET inventory, sent from Omer Ad (Schepartz lab) to Fred Ward (Cate Lab).* 

Benchling will be used for storing and querying all C-GEM sequences and annotations.

Benchling is a cloud-based 'life science data management and collaboration platform' which is free for academic use. The software is popular among molecular biologists and already in use within some (and possibly all) C-GEM labs. Benchling is accessed by web browser at [benchling.com](http://benchling.com) and provides a RESTful API for command-line interaction. Users can store sequence objects in their personal accounts or in an 'Organization' account, which provides a shared storage area that is private to members of a team. We have set up an organization called ['GEM-NET'](https://benchling.com/organizations/gem-net) that will act as a central repository for the sequences shared across the collaboration.

Benchling makes it very easy to create new sequences or search for sequences (and sequence annotations) within public databases and within personal and organization inventories. Benchling also includes a suite of tools for annotating, analyzing, aligning, and manipulating sequences. Direct links can be obtained for each sequence (with long, anonymized URLs for privacy). These links will be used when discussing sequences on other platforms.

To view read-only versions of the first two sequences shared within C-GEM, including annotations, metadata and alignments, follow the links below.
- [23S rRNA rrnb operon -clone p7_A7](https://benchling.com/s/seq-2Rs7TD81BE6AfWSFpumN)
- [pGFP3UAG-P7A7-pylT](https://benchling.com/s/seq-Dms0grV6AshRQ7Yvs8dQ)

Data 'lock-in' is not an issue with Benchling, as all data can be easily exported in open formats, allowing migration to other services if necessary. On top of the version-controlled backups maintained within the application, we will perform weekly backups (automated through the API) to guard against any data loss in the unlikely event that the website goes down.

If you are new to Benchling, you'll be led on an automatic tour of features after you [sign up](https://benchling.com/signup) for an account.

Some other useful Benchling links:

- [Join the GEM-NET organization](https://benchling.com/organizations/gem-net)
- [Feature list pdf](https://main.bnchcdn.com/static/docs/overviews/benchling-molbio-overview.pdf)
- [Feature tutorials](https://benchling.com/tutorials)

#### Benchling optional feature: biospecimen repository

We might also consider making use of the *biospecimen repository* feature of Benchling. This would allow C-GEM to maintain a searchable database of specimens (strains, sequences, primers, new mutants, etc) held across its labs. Researchers would then be able to request specimens using specific location identifiers.


## Asana: sequence discussion and sample request tracking

![Asana demo]({{site.url}}/img/data-plan/asana_sequences.jpg)
*The two C-GEM sequences shown in Asana. Each sequence has its own discussion thread.*

Asana will provide a space for discussing individual sequences, and provide a means of requesting samples from C-GEM collaborators in other labs, and keeping track of these requests.

Asana is a cloud-based task list application accessible from web browsers, a mobile app, a RESTful API, and a Slack integration. Its free version, which can accommodate multiple teams of up to 15 people each, should be adequate for C-GEM. As with Benchling, all data can be downloaded (via API), allowing migration to another service if necessary.

The initial plan for Asana is to maintain two task lists (called 'Projects' in Asana): one for request tracking and one for discussing sequences in Benchling. The request tracking list will function more like a traditional to-do list (with items being marked complete on delivery), while items on the sequence discussion list will provide a stable home for sequence-specific discussion with links to Benchling. In both cases, new list items can be created by typing directly into the list as if it were a text file, or by sending an email to a list-specific address. (Alternatively, multiple tasks can be added in bulk using the API.) Further data associated with the item (an extended description, tags, file attachments, an assignee) can be added and edited at any time. The number of items in each list can be followed using Asana's dashboard view, shown in the image below.

![Asana dashboard]({{site.url}}/img/data-plan/asana_dashboard.jpg)
*The Asana dashboard provides a quick overview of sequence/request counts over time.*

A sample request and follow-up would involve the following steps:
1. a researcher (say, Alice) would post a new list item in the **Sample_requests** list, providing a name and description, and selecting an 'assignee' (say, Bob) responsible for responding to the request.  - If the task is [created by email](https://asana.com/guide/help/email/email-to-asana#gl-email-to-project), the assignee is taken from the 'To:' entry (excluding the list address); description from the email content; and other notified 'followers' from the 'CC:' entry.
2. Bob would get a notification by email that includes details of the request and the corresponding Asana link;
3. Bob can post a comment on the request (e.g. 'Sample put in the mail today') by replying to the email or by clicking on the task in Asana;
4. Alice can respond to comments from Bob in the same way;
5. Bob will create a shared sequence in Benchling that corresponds to the sample, and create an item in the **Shared_sequences** list, providing the Benchling URL, and linking to this new item in the request comment thread;
6. Alice can mark the task complete when the sample is delivered.
These steps keep the process as simple as an email exchange, but prevent things getting out of hand as soon as there is more than one sample to be discussed.

Generic sequence-specific discussion (which will include the corresponding Benchling URLs in the description) will occur in the comment threads of the **Shared_sequences** list, and will include all samples that are transferred between labs. **Tags** can also be added to sequence items, allowing filtering of sequences with similar tags. The sequences list is a good place for any discussion where notifying others is suitable. Notifications will be delivered to anyone marked as a 'follower' of a task, which by default is everyone who is a member of the list. The follower list can be modified at any time, to tailor the notification recipients, and a user can manually unfollow a task to prevent further notifications. [Email notifications](https://asana.com/guide/help/email/email-from-asana) can be switched on and off as appropriate, with users alternatively browsing notifications in the Asana interface.

To get started, try one of the following Asana links for an introduction at a pace and depth of your choice:
- [A 2 minute click-through introduction to 'projects'](https://asana.com/guide/get-started/begin/quick-start#lessons?lesson=inbox-1)
- [A comprehensive 30 minute video walkthrough](https://asana.com/guide/get-started/begin/quick-start#lessons?lesson=inbox-1)
- [A quick-start user's guide](https://asana.com/guide/get-started/begin/quick-start)


Each C-GEM investigator should receive an email invite to join C-GEM's Asana organization. Please contact Stephen Gaffney or Jeff Townsend if you have not received an invite.


## Slack: general, high-level communication

The third and final tool is Slack, which will be used for general high-level discussion within C-GEM. Slack messaging uses topic-specific 'channels' which can either be public to everyone in C-GEM or private to a list of members, and also offers private, direct messaging. Everyone should already have an account with the GEM-NET Slack channel---please contact Stephen Gaffney or Jeff Townsend if you have not received an invite.

You can access your Slack messages using a desktop application, a mobile app, or via a web browser at [gem-net.slack.com](https://gem-net.slack.com). As with Asana, notifications are fully customizable.





