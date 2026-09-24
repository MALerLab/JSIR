<div align="center">
    <img src="./JSIR_logo.png" alt="JSIR logo" width="400" />
    <h1>JSIR: A Multi-Task, Audio-Aligned Dataset of Jazz Standard Recordings</h1>
    <p>Sihun Lee, Dasaem Jeong</p>
    <p>
        <a target="_blank" href="https://jsir-browser.onrender.com">Dataset Browser</a>
        <span> · </span>
        <a target="_blank" href="https://github.com/MALerLab/JSIR-annotator">Annotation Tool</a>
    </p>
</div>

---

JSIR (**J**azz **S**tandards dataset for **I**nformation **R**etrieval) provides beat and downbeat, chord, and structure annotations for 467 jazz recordings, spanning 28.7 hours of audio. It features four to nine recording versions for each jazz standard.

The repertoire spans a wide variety of styles and settings: from the Great American Songbook classics to hard-bop tunes, and from small combos to big band arrangements. Recordings were selected mainly for prominence and adherence to the "canonical" chord changes. All annotations were produced by the [main author](https://issyun.net) who is a jazz musician and throughly revised in several passes.

## Dataset Structure
The three layers of annotation (beats, chord, and structure) are aligned to the same beat grid, so that all events coincide with a beat.
- `beats/`: Beat and downbeat positions are given for each recording as a plain text file. Downbeats are marked with an additional `1` separated by tabs.
- `chords/`: Chord events are given as CSV files, listing onset timings and chord names in shorthand Harte syntax.
- `structure/`: Musical structure events are given as CSV files. Names for sections are structured in a six-class taxomony: `intro`, `head`, `solo`, `interlude`, `trade`, and `outro`. For head and solo sections, an additional label denotes the prominent active instruments, separated by a colon; e.g. `head:piano`, `solo:bass`, `trade:horn,drum`.
- `segments/`: The segment labels mark regions where beat and chord information can be deemed reliable enough; it excludes unaccompanied solos, rubato intros, solos with ambiguous timing or harmony, etc. **Data for beat tracking and chord estimation should only be sampled from the valid segment regions.**
- `audio/`: The collected WAV audio files are to be put here, named as `{youtube_id}.wav`.
- `lead_sheets.json` provides high-level information and the chord progression for each standard.
- `metadata.json` provides further details for individual recordings, including MusicBrainz and YouTube IDs that pin down the exact version.

## Tools
- [JSIR Browser](https://jsir-browser.onrender.com) is a web app for browsing the dataset's contents alongside audio. When visiting the website, please expect up to ~50 seconds of warmup as the hosting provider puts the app under hibernation with inactivity.
- [JSIR Annotator](https://github.com/MALerLab/JSIR-annotator) is the annotation tool purpose-built for JSIR, which features functionalities for metadata and audio collection and convenient DAW-like labeling.

## Contributing
We welcome outside contributors who may want to revise the annotations or add new data. We encourage contributors to use the JSIR Annotator when editing or creating labels as it makes the process delightfully conveinent.

## License
JSIR annotations are released under [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/). Users are free to distribute, remix, adapt, and build upon the dataset in any medium or format, so long as attribution is given to the original authors. Derivitive material should also be released under the same license.