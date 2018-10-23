# space-diff

## Description
__space-diff__ is a tool that highlights inconsistencies in word segmentation within spaced texts (such as training corpora) for any spaceless orthography.

This tool is Pure Python and requires Python 3.6+

## Installation
`pip install space-diff`

## Usage/Tutorial
Included in this repository are two sample corpora of segmented traditional Chinese which will be used in this tutorial for ease in following along. (Adapted from [Universal Dependencies' Chinese corpora](https://github.com/UniversalDependencies/UD_Chinese-GSD/tree/master).) The following instructions assume that you have __space-diff__ installed already, as well as the sample corpora.

### Command line usage
You can simply call the tool at the command line as follows:
`$ python3 space-diff [-h] [-d] corp [corp ...]`
with the optional `--help` argument, the optional `--digits` argument, and then one or more corpus file of segmented text.

By running:
`$ python3 space-diff sample_corp_a.txt sample_corp_b.txt`
you will see the that the program updates you as it processes, and then ultimately prints a human-readable summary of its findings. For your own data, just include pass the files and their paths if necessary, separated by spaces to __space-diff__.

This output allows manual review each instance of segmentation inconsistency, noting which ones are errors and which are inherent variation. The idea is to then fix those errors in your corpora before training (a segmenter) on that data.

By default, the tool considers tokens like `12`, `712`, `1 20`, and `1220` as inconsistent segmentations of a token `12`. If you wish to declutter the output with numerical cases like this, pass __space-diff__ the argument `-d` to ignore digits in its searching.
`$ python3 space-diff -d sample_corp_a.txt sample_corp_b.txt`

## License
GNU GPLv3

## Contact
Blake Perry Smith
perry.smithb@gmail.com
