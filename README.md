# st.write

`st.write` allows writing text and arguments to the Streamlit app.

## Demo app

[![Streamlit App](https://static.streamlit.io/badges/streamlit_badge_black_white.svg)](https://share.streamlit.io/dataprofessor/st-write/)

## What arguments can be written out?

In addition to being able to display text, the following can also be displayed via the `st.write()` method:
- Prints strings; works like `st.markdown()`
- Displays a Python `dict`
- Displays `pandas` DataFrame can be displayed as a table
- Plots/graphs/figures from `matplotlib`, `plotly`, `altair`, `graphviz`, `bokeh`
- And more (see [st.write on API docs](https://docs.streamlit.io/library/api-reference/write-magic/st.write))

## Code
Here's how to use st.write:
```python
import numpy as np
import altair as alt
import pandas as pd
import streamlit as st

# Example 1

st.write('Hello, *World!* :sunglasses:')

# Example 2

st.write(1234)

# Example 3

df = pd.DataFrame({
     'first column': [1, 2, 3, 4],
     'second column': [10, 20, 30, 40]
     })
st.write(df)

# Example 4

st.write('Below is a DataFrame:', df, 'Above is a dataframe.')

# Example 5

df2 = pd.DataFrame(
     np.random.randn(200, 3),
     columns=['a', 'b', 'c'])
c = alt.Chart(df2).mark_circle().encode(
     x='a', y='b', size='c', color='c', tooltip=['a', 'b', 'c'])
st.write(c)
```

## Line-by-line explanation
The very first thing to do when creating a Streamlit app is to start by importing the `streamlit` library as `st` like so:
```python
import streamlit as st
```

**Example 1**

Its basic use case is to display text and Markdown-formatted text:
```python
st.write('Hello, *World!* :sunglasses:')
```

**Example 2**

As mentioned above, it can also be used to display other data formats such as numbers:
```python
st.write(1234)
```

**Example 3**

DataFrames can also be displayed as follows:
```python
df = pd.DataFrame({
     'first column': [1, 2, 3, 4],
     'second column': [10, 20, 30, 40]
     })
st.write(df)
```

**Example 4**

You can pass in multiple arguments:
```python
st.write('Below is a DataFrame:', df, 'Above is a dataframe.')
```

**Example 5**

Finally, you can also display plots as well by passing it to a variable as follows:
```python
df2 = pd.DataFrame(
     np.random.randn(200, 3),
     columns=['a', 'b', 'c'])
c = alt.Chart(df2).mark_circle().encode(
     x='a', y='b', size='c', color='c', tooltip=['a', 'b', 'c'])
st.write(c)
```

## Further reading
In addition to [`st.write`](https://docs.streamlit.io/library/api-reference/write-magic/st.write), you can explore the other ways of displaying text:
- [st.markdown](https://docs.streamlit.io/library/api-reference/text/st.markdown)
- [st.header](https://docs.streamlit.io/library/api-reference/text/st.header)
- [st.subheader](https://docs.streamlit.io/library/api-reference/text/st.subheader)
- [st.caption](https://docs.streamlit.io/library/api-reference/text/st.caption)
- [st.text](https://docs.streamlit.io/library/api-reference/text/st.text)
- [st.latex](https://docs.streamlit.io/library/api-reference/text/st.latex)
- [st.code](https://docs.streamlit.io/library/api-reference/text/st.code)
