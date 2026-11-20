# Personal Routine

A personal Flutter app for organizing daily life, protecting sleep, studying consistently, and recovering intelligently when the planned routine is disrupted.

The working name of the app is **Ritmo**.

This is not intended to be just another task manager. Its purpose is to help the user build a more sustainable and meaningful routine while preserving autonomy and reducing unnecessary decision fatigue.

## Main Context

The user usually works from approximately 4:00 AM to 11:00 AM, following German working hours while living in Brazil.

During work hours, the user alternates between:

- programming;
- dealing directly with clients;
- academic study;
- administrative tasks.

The user also:

- attends an online university;
- plays volleyball and football several times per week;
- has a severely irregular sleep routine;
- wants to include sunlight exposure, movement, personal care and leisure;
- wants to recover academic study habits;
- wants to reduce procrastination without turning the app into a punitive productivity system.

## Product Vision

The app should function as a personal routine-support system that:

- creates structure without becoming rigid;
- reduces decision fatigue;
- helps the user recover when something is missed;
- protects sleep as a fundamental priority;
- supports work, study, health, relationships, leisure and exploration;
- uses artificial intelligence only when it genuinely adds value;
- works offline for core features;
- keeps the user in control of all recommendations.

The app should not act as a therapist, doctor, coach or unquestionable authority.

## Core Principles

1. Weekly planning comes before daily execution.
2. The routine should be structured but easy to correct.
3. The user should not need to choose the next action constantly.
4. Adaptation should happen mainly when a block is missed, delayed or explicitly reviewed.
5. Recommendations must be concrete and actionable.
6. Every recommendation must be editable, rejectable and explainable.
7. The app must work without AI.
8. AI must be an optional support layer, not a core dependency.
9. Metrics are for learning, not punishment.
10. Missed activities must not create a debt spiral.
11. Sleep has higher priority than excessive productivity.
12. Leisure, social connection and novelty are legitimate parts of the routine.

## Main Features

### 1. Weekly Planning

The user plans the upcoming week using recurring blocks and flexible blocks.

The planner should support:

- recurring routines for each weekday;
- fixed and flexible blocks;
- drag-and-drop or simple time editing;
- block categories;
- optional intentions or reasons;
- recurring work, study, exercise, leisure and sleep blocks;
- conflict and overlap detection;
- easy copying of a previous week;
- templates for different types of weeks;
- manual adjustments without destroying the original template.

Example block categories:

- work;
- programming;
- client work;
- study;
- exercise;
- volleyball;
- football;
- personal care;
- leisure;
- social;
- sleep;
- buffer;
- administration.

Each block may contain:

- title;
- category;
- start time;
- duration;
- priority;
- recurrence;
- flexibility;
- optional intention;
- optional ritual;
- optional recovery rules.

### 2. Daily Timeline

The daily timeline displays the planned day in chronological order.

It should allow the user to:

- see the current block;
- see the next block;
- start a block;
- complete a block;
- skip a block;
- postpone a block;
- cancel a block;
- mark a block as partially completed;
- open the associated ritual;
- trigger recovery suggestions.

The interface should remain simple and fast.

The app should not constantly interrupt the user with questions.

### 3. Smart Recovery

When a block is missed or delayed beyond a configurable threshold, the app should offer recovery options.

Example:

The user missed a study block from 10:00 to 11:00.

The app may suggest:

1. Move the full study block to 2:00 PM.
2. Do a reduced 25-minute version now and preserve the remaining time for another day.

A third option should be available:

- `Ask for another suggestion`

This opens a free-text input where the user can describe the situation and request another option.

Recovery suggestions should consider:

- current time;
- remaining blocks;
- block priority;
- flexible and fixed blocks;
- upcoming commitments;
- previous recovery choices;
- recurring schedule;
- recent workload;
- sleep-related constraints;
- whether the same block was already postponed;
- user-defined protected periods.

The app must always include a local fallback that works without internet or Gemini.

Possible local recovery strategies:

- move the block to the next compatible free period;
- shorten the block;
- split the block into smaller parts;
- replace it with a minimum viable version;
- postpone it to a predefined recovery window;
- remove it from today and record it for weekly review;
- preserve sleep and cancel a low-priority block.

The app must never automatically overload the rest of the day without showing the consequences.

### 4. Gemini Integration

Gemini is optional and should only be called:

- when the user explicitly asks for another suggestion;
- or when the local recovery system cannot find a reasonable option and the user allows AI assistance.

Gemini should receive only the minimum necessary context.

The integration must have:

- timeout;
- error handling;
- rate limiting;
- structured JSON responses;
- schema validation;
- local fallback;
- clear indication that the suggestion was generated by AI;
- no secret keys embedded in the application;
- no unnecessary transmission of sensitive personal data.

The AI must not diagnose mental or physical health conditions.

The AI should return structured suggestions containing:

- title;
- short explanation;
- affected blocks;
- proposed times;
- estimated duration;
- trade-offs;
- confidence level;
- whether the suggestion affects sleep or fixed commitments.

For initial personal development, a local Gemini key may be used only through a secure local configuration. For a production release, use a secure backend intermediary such as a Supabase Edge Function.

### 5. Sleep Protection

Sleep is a top-level priority.

Initial sleep features should include:

- target sleep window;
- target wake-up time;
- manual sleep logging;
- sleep duration;
- sleep regularity;
- bedtime preparation routine;
- configurable wind-down period;
- local notifications;
- warnings when the planned day conflicts with the sleep target;
- weekly sleep summary.

The app should distinguish between:

- planned sleep;
- estimated sleep;
- actual sleep;
- time spent trying to sleep.

The app must not diagnose insomnia or other sleep disorders.

### 6. Morning and Daily Anchors

The user's work begins at approximately 4:00 AM, so conventional morning routines do not fit.

The initial routine should support anchors such as:

- drinking water after waking;
- washing the face;
- starting work;
- movement or stretching after a suitable work block;
- sunlight exposure later in the morning or afternoon;
- a work shutdown ritual;
- bedtime preparation.

Anchors may be linked to:

- waking up;
- the end of a work block;
- the first available daylight period;
- the end of the workday;
- the beginning of the wind-down period.

Anchors must be editable, skippable and reschedulable.

### 7. Micro-Rituals

Micro-rituals mark transitions between activities.

They should be short, direct and optional.

Examples:

#### Starting work

- drink water;
- read the current intention;
- start the first block.

#### Starting study

- clear the desk;
- open the material;
- write one question to answer;
- start the timer.

#### Changing from programming to client work

- save current work;
- write a one-line note about where to resume;
- open the client workspace.

#### Ending work

- record unfinished tasks;
- define the next starting point;
- close work-related applications.

#### Starting sleep preparation

- reduce lights;
- put the phone away;
- complete a short calming activity;
- begin the sleep routine.

Rituals should:

- last approximately 30 seconds to 2 minutes;
- be configurable;
- be skippable;
- support presets;
- avoid unnecessary animations and friction.

### 8. Weekly Review

The weekly review takes place during planning for the next week.

It should be short and optional.

Suggested questions:

- What worked better than expected?
- Which part of the plan did not match reality?
- What did I learn about my schedule?
- What deserves more space next week?
- What should be reduced, removed or moved?
- Which activity made the week feel more alive?
- What is one concrete intention for next week?

The user may write a short weekly anchor sentence.

The sentence should be editable and should not be automatically turned into generic motivational content.

Examples:

- `Protect my sleep before adding more commitments.`
- `Make study small enough to begin.`
- `Leave room for people and activities outside work.`
- `Recover the day instead of abandoning it.`
- `One consistent hour is better than an imaginary perfect day.`

### 9. Study Support

The study module should initially remain simple.

It should support:

- subjects;
- topics;
- study sessions;
- study duration;
- active recall questions;
- review dates;
- spaced review reminders;
- session notes;
- estimated confidence;
- review history.

Do not build a complete Anki replacement during the first development cycle.

The initial goal is to help the user:

- schedule study;
- start sessions;
- retrieve knowledge actively;
- return to topics after an interval;
- maintain academic continuity.

### 10. Leisure and Novelty

Leisure is an important part of the user's current situation and must not be treated as optional waste.

The app should support:

- planned leisure blocks;
- social activities;
- physical leisure;
- creative activities;
- outdoor activities;
- exploratory activities;
- passive entertainment;
- new experiences.

The app may optionally classify leisure as:

- passive;
- social;
- physical;
- creative;
- restorative;
- exploratory.

The app must not create rankings, streaks or guilt around leisure.

Suggestions should be optional and preferably generated during weekly planning or when explicitly requested.

## Scientific Position

The app may use evidence-informed ideas, but it must not present individual studies as universal guarantees.

The project should distinguish between:

- evidence for a technique;
- evidence for a specific implementation;
- correlation;
- causation;
- philosophical interpretation;
- personal experimentation;
- clinical treatment.

Potential evidence areas include:

- implementation intentions;
- habit formation;
- active recall;
- spaced practice;
- physical activity;
- sleep regularity;
- self-determination theory;
- cognitive biases;
- behavioral activation;
- environmental design;
- adaptive interventions;
- social support;
- reflective practice.

Every important feature should eventually have an evidence record containing:

- target problem;
- exact intervention;
- source type;
- main references;
- population studied;
- limitations;
- implementation risk;
- expected cost;
- personal evaluation method.

The app must not claim that the G.A.L.I.N.H.A. method has been validated as a complete package unless research directly supports that claim.

## Technology Stack

Initial target platforms:

- Android;
- Windows;
- Linux if practical.

Recommended stack:

- Flutter;
- Dart;
- Riverpod;
- go_router;
- local database with Drift or Isar, after validating platform support and migrations;
- Supabase for authentication and remote synchronization;
- Google Calendar API;
- local notifications;
- optional Gemini integration.

Do not add dependencies without checking:

- current compatibility;
- maintenance status;
- Android support;
- Windows support;
- Linux support when relevant;
- migration strategy;
- testing support.

## Architecture

Organize by business domain, not only by technical layer.

Suggested structure:

    lib/
      app/
        app.dart
        router.dart
        providers.dart
      core/
        errors/
        logging/
        result/
        time/
      features/
        weekly_planner/
        daily_timeline/
        recovery/
        sleep/
        habits/
        rituals/
        weekly_review/
        study/
        leisure/
      data/
        local/
        remote/
        repositories/
      integrations/
        google_calendar/
        gemini/
        notifications/
        platform_blocking/
      shared/
        widgets/
        theme/
        extensions/

Features should depend on repository and service interfaces instead of directly accessing Supabase, Gemini or Google Calendar.

## Offline-first Requirements

Core functionality must work without internet.

Required behavior:

- read local data first;
- render the interface from the local database;
- save changes locally immediately;
- mark unsynchronized changes as pending;
- synchronize in the background when possible;
- log synchronization failures;
- avoid silent data loss;
- provide a visible synchronization status when useful.

For personal use, conflict resolution may initially use a documented last-write-wins strategy based on `updated_at`.

Keep synchronization logic isolated so it can be improved later.

## Supabase

Use Supabase only for:

- authentication;
- remote backup;
- synchronization;
- optional secure backend functions;
- future multi-device access.

Apply Row Level Security from the beginning.

Each user must only access their own data.

Do not commit:

- `.env`;
- API secrets;
- private keys;
- OAuth client secrets;
- signing certificates;
- personal data.

Create a `.env.example` file with placeholders.

## Google Calendar

Google Calendar integration must be optional.

The application must work without a Google account.

Before implementation, document:

- OAuth scopes;
- events created by the app;
- events imported from Google Calendar;
- event identifiers;
- duplication prevention;
- deletion behavior;
- conflict behavior;
- offline behavior.

The first implementation may use one-way sync if bidirectional sync is too risky. Do not claim bidirectional synchronization until it has been tested.

## App and Website Blocking

Blocking applications and websites is platform-dependent.

Android may require:

- Usage Access;
- Accessibility Service;
- special permissions;
- platform-specific services;
- careful compliance with Play Store policies.

Windows requires a separate implementation strategy.

Do not assume that Flutter alone can reliably block all applications or websites.

Start with:

- focus mode;
- reminders;
- local notifications;
- links to native system controls;
- reversible restrictions.

Any real blocking feature must include:

- emergency bypass;
- recovery path;
- clear permissions;
- visible status;
- disable option;
- no risk of locking the user out of the device.

## Privacy

The app should collect the minimum necessary data.

Requirements:

- minimize data sent to Gemini;
- allow deletion of local data;
- allow deletion of remote data;
- document external integrations;
- protect user-owned data;
- avoid health claims;
- avoid sending full journal entries to external services by default.

## Visual Direction

The visual style should be cozy and calm, inspired by:

- coffee;
- cats;
- warm lighting;
- notebooks;
- simple home environments;
- soft colors.

Suggested palette:

- background: `#FDFBF7`;
- primary text: `#3D3A36`;
- sage accent: `#6B8F71`;
- warm terracotta: `#C4956A`;
- soft brown: `#8A6A50`;
- light cream card: `#FFFDF8`.

Use:

- rounded cards;
- generous spacing;
- clear typography;
- subtle shadows;
- minimal animation;
- high contrast;
- accessible controls.

The interface should be cozy without becoming childish, distracting or visually overloaded.

## Development Rules

The AI developer must:

- inspect the repository before editing;
- work directly in the workspace when possible;
- make small incremental changes;
- preserve unrelated user changes;
- avoid rewriting files unnecessarily;
- avoid implementing future features prematurely;
- explain platform limitations;
- use verified APIs;
- run formatting, analysis and tests;
- report all modified and created files;
- wait for approval before continuing to the next stage.

After each stage, run:

    flutter pub get
    dart format .
    flutter analyze
    flutter test

## Implementation Stages

### Stage 1

- initialize the Flutter project;
- create the domain-oriented structure;
- configure routing;
- create the theme;
- create environment configuration;
- create a basic home screen;
- add minimal tests;
- do not implement integrations yet.

### Stage 2

- implement local routine and time-block models;
- implement repositories;
- implement weekly planning;
- implement recurring blocks;
- implement daily timeline.

### Stage 3

- implement block states;
- implement delays and missed blocks;
- implement local recovery rules;
- implement manual rescheduling.

### Stage 4

- implement optional Gemini integration;
- add structured response validation;
- add timeout and fallback behavior;
- test invalid and unavailable responses.

### Stage 5

- implement habits;
- implement contextual anchors;
- implement micro-rituals;
- implement local notifications.

### Stage 6

- implement sleep tracking;
- implement wind-down routines;
- implement weekly sleep summaries.

### Stage 7

- implement weekly review;
- implement leisure and novelty;
- implement study sessions;
- implement active recall and spaced review basics.

### Stage 8

- implement Supabase authentication and synchronization;
- implement Google Calendar integration;
- test offline and online transitions.

### Stage 9

- investigate Android and Windows focus/blocking features separately;
- implement only after validating permissions and reversibility.

## Initial Claude Instruction

The repository may be empty.

First, read this README and treat it as the initial project specification.

Before editing:

1. confirm the current directory;
2. verify that Flutter and Dart are available;
3. inspect the repository;
4. show a short plan for Stage 1;
5. do not implement Gemini, Google Calendar, Supabase synchronization or application blocking yet.

Then implement only Stage 1.

After implementation:

1. run `flutter pub get`;
2. run `dart format .`;
3. run `flutter analyze`;
4. run `flutter test`;
5. report created files;
6. report modified files;
7. report executed commands and results;
8. report known limitations;
9. wait for approval before continuing.

Work directly in the workspace.

Do not return the entire project as one large Markdown file.

Do not create a ZIP yet.

Do not request or expose secret keys, tokens, credentials or personal data.
