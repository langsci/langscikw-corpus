# Language Science Press book corpus

Here you can find corpora containing Language Science Press publications.

Currently two corpora are available: 

* corpus_tex.gz (37.8 MB, 128 million characters): Raw TeX code books.
* corpus_detex.gz (22.4 MB, 72 million characters): Detexed books, i.e. stripped of most TeX commands. Some data loss is possible.

Both contain 144 (mostly) English books published before June 2021. They are the standard corpora for the [langscikw](https://github.com/langsci/langscikw) package.

# Usage 

## With langscikw

Install the package:

```
pip install langscikw
```

Run command-line tool if corpus files are in the current directory:

```
langscikw your-input-file.txt
```

Otherwise supply corpus paths (300 is the desired number of keywords):

```
langscikw your-input-file.txt 300 path/corpus_tex.gz path/corpus_detexed.gz
```

## On its own
The files can be extracted using Python's [joblib](joblib.readthedocs.io/) module. You will receive a list containing 144 strings (one string per book).

```python
import joblib
corpus = joblib.load("corpus_tex.gz")
```


