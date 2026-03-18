# WCAG 2.1 AA Summary

**Citation:** Web Content Accessibility Guidelines (WCAG) 2.1, W3C Recommendation, June 5, 2018
**Source:** https://www.w3.org/TR/WCAG21/
**Date:** June 5, 2018 (W3C Recommendation)
**Note:** WCAG 2.2 was published October 5, 2023 and adds additional criteria, but WCAG 2.1 AA remains the standard referenced in most regulatory and procurement contexts (including the DOJ's 2024 Title II rule).

---

## Overview

WCAG 2.1 provides guidelines for making web content accessible to people with disabilities, including visual, auditory, physical, speech, cognitive, language, learning, and neurological disabilities. The guidelines are organized around four principles: Perceivable, Operable, Understandable, and Robust (POUR).

**Conformance levels:** Each success criterion is assigned a level — A (minimum), AA (target for most regulatory requirements), or AAA (highest). Level AA conformance requires meeting all Level A and Level AA criteria.

## Principle 1: Perceivable

Information and user interface components must be presentable in ways users can perceive.

### Level A Criteria

| Criterion | Summary |
|---|---|
| **1.1.1 Non-text Content** | All non-text content (images, charts, icons) has a text alternative that serves the equivalent purpose |
| **1.2.1 Audio-only and Video-only** | Alternatives provided for prerecorded audio-only and video-only content |
| **1.2.2 Captions (Prerecorded)** | Captions provided for all prerecorded audio content in synchronized media |
| **1.2.3 Audio Description or Media Alternative** | Audio description or text alternative for prerecorded video |
| **1.3.1 Info and Relationships** | Information, structure, and relationships conveyed through presentation can be programmatically determined |
| **1.3.2 Meaningful Sequence** | Correct reading sequence can be programmatically determined |
| **1.3.3 Sensory Characteristics** | Instructions do not rely solely on sensory characteristics (shape, color, size, location, sound) |
| **1.4.1 Use of Color** | Color is not used as the only visual means of conveying information |
| **1.4.2 Audio Control** | Mechanism to pause or stop audio that auto-plays for more than 3 seconds |

### Level AA Criteria

| Criterion | Summary |
|---|---|
| **1.3.4 Orientation** | Content does not restrict display to a single orientation (portrait or landscape) unless essential |
| **1.3.5 Identify Input Purpose** | The purpose of input fields collecting user information can be programmatically determined |
| **1.4.3 Contrast (Minimum)** | Text and images of text have a contrast ratio of at least 4.5:1 (3:1 for large text) |
| **1.4.4 Resize Text** | Text can be resized up to 200% without loss of content or functionality |
| **1.4.5 Images of Text** | Text is used rather than images of text (with limited exceptions) |
| **1.4.10 Reflow** | Content can be presented without horizontal scrolling at 320 CSS pixels wide (and 256px high for horizontal text) |
| **1.4.11 Non-text Contrast** | UI components and graphical objects have a contrast ratio of at least 3:1 against adjacent colors |
| **1.4.12 Text Spacing** | No loss of content or functionality when users adjust text spacing (line height, paragraph spacing, letter spacing, word spacing) |
| **1.4.13 Content on Hover or Focus** | Additional content triggered by hover or focus is dismissible, hoverable, and persistent |

## Principle 2: Operable

User interface components and navigation must be operable.

### Level A Criteria

| Criterion | Summary |
|---|---|
| **2.1.1 Keyboard** | All functionality is operable through a keyboard interface |
| **2.1.2 No Keyboard Trap** | Keyboard focus can be moved away from any component using the keyboard |
| **2.1.4 Character Key Shortcuts** | If single-character key shortcuts exist, they can be remapped or disabled |
| **2.2.1 Timing Adjustable** | Users can extend, adjust, or disable time limits (with limited exceptions) |
| **2.2.2 Pause, Stop, Hide** | Moving, blinking, or auto-updating content can be paused, stopped, or hidden |
| **2.3.1 Three Flashes or Below Threshold** | Content does not flash more than three times per second |
| **2.4.1 Bypass Blocks** | Mechanism to bypass blocks of content repeated on multiple pages (e.g., skip navigation) |
| **2.4.2 Page Titled** | Pages have descriptive titles |
| **2.4.3 Focus Order** | Focusable components receive focus in a meaningful sequence |
| **2.4.4 Link Purpose (In Context)** | Purpose of each link can be determined from the link text or its context |
| **2.5.1 Pointer Gestures** | Multipoint or path-based gestures have single-pointer alternatives |
| **2.5.2 Pointer Cancellation** | Functions triggered by single pointer can be cancelled |

### Level AA Criteria

| Criterion | Summary |
|---|---|
| **2.4.5 Multiple Ways** | More than one way to locate a page within a set of pages (e.g., search, site map, navigation) |
| **2.4.6 Headings and Labels** | Headings and labels describe topic or purpose |
| **2.4.7 Focus Visible** | Keyboard focus indicator is visible |
| **2.5.3 Label in Name** | The accessible name of UI components contains the visible text label |
| **2.5.4 Motion Actuation** | Functions triggered by device motion (e.g., shaking) can also be operated by UI components and motion response can be disabled |

## Principle 3: Understandable

Information and the operation of the user interface must be understandable.

### Level A Criteria

| Criterion | Summary |
|---|---|
| **3.1.1 Language of Page** | Default human language of each page can be programmatically determined |
| **3.2.1 On Focus** | Components do not change context when they receive focus |
| **3.2.2 On Input** | Changing a form setting does not automatically cause a change of context unless user is advised beforehand |
| **3.3.1 Error Identification** | Input errors are automatically detected and described to the user in text |
| **3.3.2 Labels or Instructions** | Labels or instructions are provided when content requires user input |

### Level AA Criteria

| Criterion | Summary |
|---|---|
| **3.1.2 Language of Parts** | Language of each passage or phrase can be programmatically determined |
| **3.2.3 Consistent Navigation** | Navigation mechanisms are consistent across a set of pages |
| **3.2.4 Consistent Identification** | Components with the same functionality are identified consistently |
| **3.3.3 Error Suggestion** | If an input error is detected and suggestions are available, they are provided |
| **3.3.4 Error Prevention (Legal, Financial, Data)** | For pages causing legal commitments or financial transactions: submissions are reversible, data is checked for errors, or a confirmation mechanism is provided |

## Principle 4: Robust

Content must be robust enough to be interpreted reliably by a wide variety of user agents, including assistive technologies.

### Level A Criteria

| Criterion | Summary |
|---|---|
| **4.1.1 Parsing** | Elements have complete start and end tags, are nested correctly, and do not contain duplicate attributes (note: relaxed in WCAG 2.2) |
| **4.1.2 Name, Role, Value** | All UI components have accessible names, roles, states, and values that can be programmatically determined |

### Level AA Criteria

| Criterion | Summary |
|---|---|
| **4.1.3 Status Messages** | Status messages can be programmatically determined through role or properties so they are presented to the user by assistive technologies without receiving focus |

## Criteria Most Relevant to Web Applications (ClarifiED, loanlimit.app)

For a loan recommendation engine and compliance tool, these criteria deserve particular attention:

- **1.4.3 / 1.4.11 Contrast** — Data tables, charts, form elements, and interactive controls must meet contrast requirements
- **2.1.1 Keyboard** — All functionality (filtering, sorting, selecting loans, running calculations) must work via keyboard
- **2.4.7 Focus Visible** — Users navigating with keyboards must see where focus is at all times
- **3.3.1-3.3.4 Input Assistance** — Error messages must be specific, and financial/legal transactions must have confirmation mechanisms
- **4.1.2 Name, Role, Value** — Custom UI components (dropdowns, sliders, data grids) must expose correct semantics to screen readers
- **4.1.3 Status Messages** — Dynamic updates (calculation results, validation messages) must be announced to assistive technology users
- **1.3.1 Info and Relationships** — Data tables must use proper markup (th, scope, headers) for screen readers
- **1.4.10 Reflow** — The application must work at 320px width without horizontal scrolling

## Notes on Completeness

This summary covers all Level A and Level AA success criteria in WCAG 2.1. The full normative text, including sufficient techniques and understanding documents, is available at the W3C link above. WCAG 2.2 (October 2023) adds additional criteria not listed here; institutions may begin referencing 2.2 in procurement requirements.
