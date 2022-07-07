### This repo is modified according to the initial [python2 version](https://github.com/davisvideochallenge/davis-2017)
-----

# Tools for Evaluating DAVIS Dataset (for Semi-supervised VOS)

## Requirements
- used packages

  You can install them by `pip install -r python/requirements.txt`

- DAVIS dataset

  You need to download and unzip the [DAVIS2017 trainval dataset](https://data.vision.ee.ethz.ch/csergi/share/davis/DAVIS-2017-trainval-480p.zip) to `/data`.
  You can run `data/get_davis.sh` to download it.
  **Only need DAVIS 2017. Evaluation of DAVIS 2016 is also possible**

  The data structure should be:
  ```xml
  - data/
    - DAVIS/
      - Annotations
      - JPEGImages
      - ImageSets
      - Scribbles
  ```

## Evaluation Command
Before evaluation, you should add PYTHONPATH:

    `export PYTHONPATH=$(pwd)/python/lib`

### Evaluate on DAVIS 2017


    `python tools/eval.py -i path-to-your-results -o results.yaml --year 2017 --phase val`

#### Evaluate on DAVIS 2016

    `python tools/eval.py -i path-to-your-results -o results.yaml --year 2016 --single-object --phase val`



## Code Structure
The directory is structured as follows:

 * `/cpp`: Implementation and python wrapper of the temporal stability measure.

 * `/python/tools`: contains scripts for evaluating segmentation.
     - `eval.py` : evaluate a technique and store results in HDF5 file
     - `eval_view.py`: read and display evaluation from HDF5.
     - `visualize.py`: visualize segmentation results.

 * `/python/lib/davis`  : library package contains helper functions for parsing and evaluating DAVIS

 * `/data` :
     - `get_davis.sh`: download input images and annotations.


Citation
--------------

Please cite `DAVIS` in your publications if it helps your research:

    @inproceedings{Perazzi_CVPR_2016,
      author    = {Federico Perazzi and
                   Jordi Pont-Tuset and
                   Brian McWilliams and
                   Luc Van Gool and
                   Markus Gross and
                   Alexander Sorkine-Hornung},
      title     = {A Benchmark Dataset and Evaluation Methodology for Video Object Segmentation},
      booktitle = {The IEEE Conference on Computer Vision and Pattern Recognition (CVPR)},
      year      = {2016}
    }

    @article{Pont-Tuset_arXiv_2017,
      author  = {Jordi Pont-Tuset and
                 Federico Perazzi and
                 Sergi Caelles and
                 Pablo Arbel\'aez and
                 Alexander Sorkine-Hornung and
                 Luc {Van Gool}},
      title   = {The 2017 DAVIS Challenge on Video Object Segmentation},
      journal = {arXiv:1704.00675},
      year    = {2017}
    }


Terms of Use
--------------
DAVIS is released under the BSD License (see [LICENSE](LICENSE) for details)

Original Repo Author
------------------
- [Federico Perazzi](https://graphics.ethz.ch/~perazzif)
- [Jordi Pont-Tuset](http://jponttuset.github.io)


