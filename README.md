# ERP CORE (Compendium of Open Resources and Experiments)

Emily S. Kappenman(1,2), Jaclyn L. Farrens(1), Wendy Zhang(1,2), Andrew X. Stewart(3), & Steven J. Luck(3)

1. San Diego State University, Department of Psychology, San Diego, CA, 92120
2. SDSU/UC San Diego Joint Doctoral Program in Clinical Psychology, San Diego, CA, 92120
3. University of California, Davis, Center for Mind & Brain and Department of Psychology, Davis, CA, 95616

The ERP CORE (<https://doi.org/10.18115/D5JW4R>) is a freely available online resource consisting of optimized
paradigms, experiment control scripts, example data from 40 neurotypical adults, data processing pipelines and
analysis scripts, and a broad set of results for 7 widely used ERP components: N170, mismatch negativity (MMN),
N2pc, N400, P3, lateralized readiness potential (LRP), and error-related negativity (ERN).

## What's Included

1. Raw EEG data for 6 task paradigms (yielding 7 ERP components) from 40 participants, located in subject folders sub-001 through sub-040
2. The event code schemes for all experiment paradigms
3. The task stimuli used for eliciting N170, MMN, and N400, located in the `stimuli/` folder
4. Demographic information for all 40 participants (`participants.tsv` and `participants.json`)

## Tasks

| Task | ERP Component(s) | Description |
|------|-------------------|-------------|
| flankers | ERN, LRP | Eriksen flanker task (compatible/incompatible arrow flankers) |
| MMN | MMN | Passive auditory oddball |
| N170 | N170 | Face perception (faces, cars, scrambled) |
| N2pc | N2pc | Visual search |
| N400 | N400 | Word pair judgment (related/unrelated) |
| P3 | P3 | Active visual oddball |

## BIDS Restructuring Notes

The original dataset from NEMAR used `ses-*` (session) directories for each ERP paradigm.
This was corrected because all 6 paradigms were administered in a single recording session
(Kappenman et al., 2021). The following changes were made:

- Removed session-level directories; data is now organized as `sub-XXX/eeg/sub-XXX_task-YYY_*`
- Merged `task-ERN` and `task-LRP` into `task-flankers`, since both ERP components come from the same flanker paradigm recording (identical raw data)
- Fixed `EEGCoordinateSystem` from invalid `"ARS"` to `"EEGLAB"` (Anterior-Left-Superior orientation)
- Fixed `task-N170_events.json`: replaced invalid range-based Levels keys (e.g., `"1-40"`) with a Description field
- Fixed `task-MMN_events.json` and `task-N2pc_events.json`: added missing event value definitions
- Consolidated duplicate `electrodes.tsv` and `coordsystem.json` files using BIDS inheritance (one per subject instead of one per task)
- Fixed `dataset_description.json` name from `"ERP CORE N400"` to `"ERP CORE"`

## Contact

Experiment control files, archival copies of the EEGLAB/ERPLAB scripts and accessory files
used for analyzing the data, and the processed data can all be found at <https://doi.org/10.18115/D5JW4R>.

To download the latest versions of the scripts or to report bugs, visit <https://github.com/lucklab/ERP_CORE>.

For other questions about the ERP CORE, contact us at erpbootcamp@gmail.com.
Additional ERP resources are available on the ERP Info website (<https://erpinfo.org>).
