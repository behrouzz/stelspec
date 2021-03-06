**Author:** [Behrouz Safari](https://behrouzz.github.io/)<br/>
**License:** [MIT](https://opensource.org/licenses/MIT)<br/>

# stelspec
*A python package for retrieving and analysing stellar spectra (ELODIE-SOPHIE Archive)*


## Installation

Install the latest version of *stelspec* from [PyPI](https://pypi.org/project/stelspec/):

    pip install stelspec

Requirements are *requests*, *numpy* and *pandas*.

## Quick start

Let's start by creating an Elodie instance by passing an object name:

```python
import stelspec as sp

el = sp.Elodie('HD217014')
```

You can access two tables, CCF and Spectra, as pandas DataFrame.

```python
# table: Cross-Correlation Functions
df_ccf = el.ccf()

# table: Spectra
df_spc = el.spec()
```

You can also download spectra as FITS file, whether in *s1d* or *s2d* format:

```python
# download spectrum FITS file in s1d format
el.get_spec(dataset=19960831, imanum='0017', path='data/', s1d=True)

# download spectrum FITS file in s2d format
el.get_spec(dataset=19960831, imanum='0017', path='data/', s1d=Flase)
```

The same process can be done for Sophie, except that instead of *dataset* and
*imanum*, you should pass the *seq* number.

For a brief help on the structure of FITS files, see [ELODIE](http://atlas.obs-hp.fr/elodie/500/download.html) and [SOPHIE](http://atlas.obs-hp.fr/sophie/spec_help.html).
