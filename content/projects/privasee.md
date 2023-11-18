---
title: "PrivaSee: Building a privacy policy comparison interface"
date: 2020-05-31
cover: 
  image: "/privasee-cover.png"
---

I built PrivaSee as part of my senior thesis in Computer Science. When you're evaluating a privacy policy, an important task for users is to understand how that policy is **different** from other policies. In other words, is there anything weird about this policy?

The goal of PrivaSee is to automatically provide users with information about the data practices described in policies in relation to the corpus of privacy policies online as a whole. It builds off the [OPP-115 Corpus](https://usableprivacy.org/data), a corpus of 115 privacy policies collected by the Usable Privacy Project. 

The research is actually still ongoing since the lab is working on revisions for a paper I submitted. Here's a high-level overview:

### What it is

The system presents two views to the user for each policy. First, there is a “global” view which scores privacy policies on their “similarity to the corpus” overall. It also scored the policies on how similar they were to the norm within different categories of data practices (like Third Party Sharing or User Access).

Clicking on a policy name takes the user to a “local” view that shows the text of the policy with further similarity indicators shown for each segment of text. 

### The algorithms

The project was developed in Python, mainly using TF-IDF and gensim doc2vec, and the demo system was made using Flask/Jinja2. 

Here’s a high-level diagram of how I created the scoring algoirthm. I used doc2vec to generate a document vector for the corpus (or the corpus within a given data practice). Then, for each individual policy, I scored the similarity by taking the distance of the individual document vector to the corpus vector:

![Product page](/vectors.png)

I also used TF-IDF and some basic frequency calculations to highlight important and uncommon words to the user. 

### Thoughts

I really care about privacy and I hope I have the chance to work on this again soon. Also, the [original doc2vec paper](https://arxiv.org/abs/1405.4053) is a super cool read. 

I think this is a really important area for people with domain expertise to work on, to try to help shape policies that protect people's rights as we venture on into the digital world. Empowering users and protecting their rights is is definitely something I try to keep in mind for other projects I build. 
