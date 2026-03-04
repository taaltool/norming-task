# jsPsych Code for Psycholinguistic Norming Task

A jsPsych 8 experiment for eliciting participants' responses to word cues. Uses the survey-html-form plugin extended with dynamically generated input fields — each response entered in a separate field — making it suitable for collecting semantic, associative, and other property generation norms. Built for online deployment via [JATOS](https://www.jatos.org/).

## Features

- **Dynamic chained input fields** — new response fields appear automatically as the participant types, with no artificial upper limit on the number of responses
- **Category-aware stimulus randomisation** — custom shuffle algorithm ensures a minimum gap between items from the same semantic category, with automatic fallback if the constraint cannot be satisfied
- **Flexible practice block** — participants can repeat instructions and practice trials as many times as needed; the option to skip practice is unlocked after the first repetition
- **Manual progress bar** — accurate progress tracking that ignores repeated instruction/practice loops and back-navigation, so the bar always reflects true progress through the main experiment
- **JATOS integration** — deployed via JATOS for online data collection; experiment hooks into `jatos.onLoad()` and `jatos.endStudy()` to submit a complete CSV at the end of the session
- **Interaction metadata** — number of window blur/focus events and fullscreen exits are recorded, providing a basic attention check
- **Responsive layout** — clean, minimal design tested down to 370 px viewport width; mobile-specific button stacking via CSS media queries

## Stack

| Library | Version |
|---|---|
| jsPsych | 8.2.1 |
| plugin-survey-html-form | 2.1.0 |
| plugin-html-button-response | 2.1.0 |
| plugin-browser-check | 2.1.0 |
| plugin-fullscreen | 2.1.0 |

## File overview

```
experiment.html   — main experiment script
stimuli.js        — stimulus list (cue, category, frequency metadata)
style.css         — custom styles
endPage.html      — post-redirect thank-you page
```

## Data output

One CSV row per trial. Key columns:

| Column | Description |
|---|---|
| `stimulus` | Czech cue word |
| `answers_joined` | Pipe-separated list of responses (`action1 \| action2 \| …`) |
| `n_answers` | Number of responses given |
| `rt` | Response time (ms) |
| `subject_id` | Random 15-character participant ID |
| `phase` | `practice` or `main` |
| `category` | Semantic category of the cue |

## Citation

You are welcome to use and adapt this code for your own research. If you do so, please cite:

> Vokáčová, M. (2026). *jsPsych Code for Psycholinguistic Norming Task* [Computer software]. GitHub. [https://github.com/espressomartiny/norming-task]
