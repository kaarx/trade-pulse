# Trade Pulse

## Overview

A read-only analysis tool that uses Reddit's Data API to identify
recurring workflow, software, and business pain points in Australian
trade communities---starting with electricians.

The goal is to surface underserved problems that can inform the creation
of better tools, services, and workflows for tradespeople.

------------------------------------------------------------------------

## Key Principles

-   **Read-only**: No posting, commenting, voting, or user interaction
-   **API-first**: Uses Reddit's official Data API only (no scraping)
-   **Privacy-conscious**: Removes user-identifying data
-   **Compliant**: Adheres to Reddit API policies and rate limits
-   **Incremental**: Only collects new/updated content

------------------------------------------------------------------------

## Initial Scope

### Target Subreddits

-   r/AusElectricians
-   r/AskAusElectricians

### Data Collected

-   Post titles and bodies
-   Selected top-level comments
-   Timestamps
-   Post metadata (score, flair, etc.)

------------------------------------------------------------------------

## What the Tool Does

1.  **Scheduled Collection**
    -   Runs on a schedule (e.g. daily)
    -   Fetches new posts via Reddit API
2.  **Normalization**
    -   Converts raw Reddit data into structured records
    -   Cleans text and removes noise
3.  **Analysis**
    -   Detects recurring themes (e.g. quoting issues, scheduling pain)
    -   Groups similar problems
4.  **Reporting**
    -   Generates weekly summaries
    -   Highlights emerging patterns and opportunities

------------------------------------------------------------------------

## Example Outputs

### Example 1

Multiple posts about poor-quality job leads: → Theme: *Lead
qualification tools for small contractors*

### Example 2

Repeated complaints about admin overhead: → Theme: *Scheduling and admin
workflow inefficiencies*

------------------------------------------------------------------------

## Architecture (High-Level)

    Reddit API → Collector → Storage → Analyzer → Report Generator

### Components

-   **Collector**: Handles API calls and incremental sync
-   **Storage**: SQLite (initial) or Postgres (scalable)
-   **Analyzer**: NLP / clustering logic
-   **Reporter**: Markdown / HTML summaries

------------------------------------------------------------------------

## Compliance & Ethics

-   Uses OAuth authentication
-   Descriptive User-Agent
-   Conservative request rate
-   No scraping outside API
-   Removes deleted content
-   No user profiling or targeting

------------------------------------------------------------------------

## Future Enhancements

-   Expand to other trades (plumbing, carpentry, HVAC)
-   Trend tracking over time
-   Idea scoring and prioritisation engine

------------------------------------------------------------------------

## Vision

Build a continuous "problem radar" for real-world trades---turning raw
discussions into actionable product and business opportunities.

