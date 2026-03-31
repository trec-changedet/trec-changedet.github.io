# TREC Change Detection

Change Detection is a new track for TREC 2026.  The goal of the track is to consider information over a day-to-day review process and think about how systems could surface content by indicating how it is relevant to aspects of the topic aside from "relevance".

## Chronology

The model of the track is a user with a daily inbox to work through. The vast majority of documents in the daily inbox are irrelevant to that user, but a few might be. Systems need to be able to surface those documents.

Systems must process the document collection in chronological order, in one-day chunks. The dataset we are using, RAGTIME1, has timestamps on each documents as `2021-08-01T02:08:10.000Z` and the documents are in timestamp order. All documents with the timestamp prefix `2021-08-01` would be considered as being on the same day.

Systems can know what happened "in the past", but not "in the future". So collection statistics are available from days current and past, but not in the future. This means that you can't run a retrieval on the entire collection while running the task. You may use any dataset from prior to 2021-08-01 as background or training data.

## Intent

The user has a single topic of interest (this is TREC after all), and that topic is described textually with a narrative paragraph. This information need is further characterized by a set of _analytic questions_. For example, if the topic concerned a technology like semiconductors, a question might be "Where are semiconductors being manufactured?"

At each day of the task, the system has three goals:

1. Rank some or all of the documents in the inbox in order of predicted relevance to each analytic question,
2. Rank order the questions that have relevant information that day, in order of importance for that day, and
3. To propose new questions outside the current set, attaching proposed relevant documents to those questions and ranking them together with the existing set of questions.

## Metrics

The primary metric is correctly ranking the questions for that day. A secondary metric is ranking documents for each question. We will also score proposed questions. Specific metrics are identified in the guidelines, and of course in TREC tradition many metrics will be computed.

## Coordinators

- Kristine Rogers
- Ian Soboroff
- Advisory board:
    - David Grossman
    - John Frank
    - Peter Gantz
    - Megan Niemczyk
