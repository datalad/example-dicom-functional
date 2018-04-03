# Example DICOM dataset of a functional BOLD fMRI scan

These data can be useful for tests and demos. Enjoy!

Information on stimulus type and timing are available in the `events.tsv` file
in [BIDS format](http://bids.neuroimaging.io/).

This dataset is a minimal excerpt of one aspect of the studyforrest extension
dataset published in:

    Sengupta, A., Kaule, F. R., Guntupalli, J. S., Hoffmann, M. B., Häusler, C.,
    Stadler, J. & Hanke, M. (2016). A studyforrest extension, retinotopic mapping
    and localization of higher visual areas. Scientific Data, 3:160093.

  http://www.nature.com/articles/sdata201693

## Flavors

Three sizes of this dataset are provided in three branches to cater to
different use cases

- **master**

  A full single run of a block design visual localizer experiment with
  six images categories, where each category appeared in two blocks.
  156 volumes.

- **half**

  Only the first half of the experiment run -- still with all six
  image categories, but only one block for each category. This variant
  can be processed quicker, but may be less useful for demoing a real
  analysis. 78 volumes.

- **1block**

  Even shorter than **half**, covering the first stimulation block include
  pre- and post-stimulation rest phase only. 18 volume.
  This is mostly useful for technical validation.

## Anonymization

DICOM header were anonymized, and certain field values have been reset using
 the following command

    gdcmanon --dumb --remove 400,500 --remove 12,62 --remove 12,63 \
      --replace 0008,103E,func_task-oneback_run-1 \
      --replace 0018,1030,func_task-oneback_run-1 \
      --replace 0008,1030,Hanke_Stadler^0083_transrep2 \
      --replace 0010,0010,Jane_Doe \
      --replace 0010,0020,02 \
      --replace 0010,0040,F \
      --replace 0010,1010,42 \
      --replace 0010,1030,75 \
      --replace 0010,0030,19660101 \
      -i ... -o ...


## Acknowledgements

This work was supported by the German Federal Ministry of Education and
Research (BMBF 01GQ11112), the German federal state of Saxony-Anhalt and the
European Regional Development Fund (ERDF), Project: Center for Behavioral Brain
Sciences, Imaging Platform.
