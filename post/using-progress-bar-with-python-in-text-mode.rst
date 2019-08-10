.. post:: 01 05, 2019

Using Progress Bar with Python in Text Mode
===========================================

Since I often have long running batch processing scripts in python I was
looking for a way to implement a progress bar. On my search I found a
nice tool called `tqdm <https://github.com/tqdm/tqdm>`__.

With tqdm it is very easy to show a progress bar in text mode (and
jupyter notebooks). My first usage is here on my MLTB project: `tools.py
Line
52 <https://github.com/PhilipMay/mltb/blob/af4515097184c2875591552153cb45c497f2881a/mltb/tools.py#L52>`__
