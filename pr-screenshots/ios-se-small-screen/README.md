# Lotti small-screen UI audit

Viewport: 320 × 568 logical pixels at 2× device pixel ratio, matching the
first-generation iPhone SE layout size.

## Walkthrough

The repository screenshot catalog was run across its phone cases, producing
296 baseline screenshots from 135 cataloged scenarios. The review covered:

- Daily OS capture, reconcile, drafting, refine, agenda, timeline, activity,
  date navigation, and large-text states
- Tasks, projects, task detail, filters, agent cards, and project flows
- Journal overview/detail, filters, linked activity, recording playback,
  transcript review, and session rating
- Agents, pending wakes, templates, instances, souls, reports, and filters
- AI settings, providers, profiles, model configuration, and AI Impact
- Settings, advanced settings, sync, categories, labels, measurables,
  dashboards, habits, recording style, keyboard shortcuts, and celebrations
- Insights and time analysis
- Events overview, detail, timeline, and editing
- Onboarding and What's New

Screens that failed only because a screenshot test asserted that lazy,
below-the-fold content was already built were reviewed visually and were not
counted as layout defects.

## Confirmed defects

| Severity | Screen | Defect | Evidence |
| --- | --- | --- | --- |
| High | Daily OS day view | The drafted-plan footer overflowed vertically; after compacting it, the remaining timeline could be shorter than its toolbar. Phone layouts now use the compact review menu and the toolbar yields to the scrollable timeline when height is critically constrained. | [before](before/day_mini_02_timeline_dark.png) · [after](after/day_mini_02_timeline_dark.png) |
| High | Daily OS refine | The fixed voice template overflowed the modal on a short phone. It now uses the same fill-or-scroll, bottom-anchored behavior as Capture. | [before](before/mini_09_refine_dark.png) · [after](after/mini_09_refine_dark.png) |
| High | Session rating | The question form and actions overflowed below the bottom sheet. The form now scrolls, keeping every question and action reachable. | [before](before/session_rating_mobile_dark.png) · [after](after/session_rating_mobile_dark.png) |
| High | Speech transcript review | Transcript date and processing-time rows overflowed horizontally. They now wrap while preserving both values. | [before](before/recording_transcripts_mobile_dark.png) · [after](after/recording_transcripts_mobile_dark.png) |
| Medium | Agent pending wakes | Status pills, time metadata, and trailing actions competed for one fixed row and overflowed. Pills now wrap in their own flexible area. | [before](before/agents_pending_wakes_mobile_dark.png) · [after](after/agents_pending_wakes_mobile_dark.png) |
| Medium | AI Impact | The selected KPI delta chip was flexed too narrowly beside its comparison label. The chip now keeps its intrinsic width and the label takes the remaining space. | [before](before/ai_usage_mobile_dark.png) · [after](after/ai_usage_mobile_dark.png) |
| Medium | Daily OS drafting | The disabled Accept/Decline controls on a learning nudge overflowed their card. The controls now wrap. | [before](before/learning_nudge_mobile_dark.png) · [after](after/learning_nudge_mobile_dark.png) |
| Medium | What's New | The release-position dots were four pixels wider than the center slot on a 320px footer. The noninteractive indicator scales down to the available slot. | [before](before/whats_new_past_release_mobile_dark.png) · [after](after/whats_new_past_release_mobile_dark.png) |
| Medium | Daily OS at 2× text | Review reasons consumed the entire day view and category chips could overflow. Large text now suppresses the explanatory rows, and category labels ellipsize within their chip. | [before](before/day_mini_08_timeline_dark_ts20.png) · [after](after/day_mini_08_timeline_dark_ts20.png) |
| Medium | Daily OS refine at 2× text | The short refine modal could not keep the orb and actions reachable at large text. Its bottom-anchored scroll fallback now preserves the controls. | [before](before/mini_22_refine_dark_ts20.png) · [after](after/mini_22_refine_dark_ts20.png) |

## Result

Every confirmed overflow has a widget regression test at the failing
constraint. The affected screens were re-rendered at 320 × 568, including
light/dark variants where the harness provides them, and the after captures
contain no RenderFlex overflow stripes.
