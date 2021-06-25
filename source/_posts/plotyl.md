---
title: Plotly
tags: Plotly

---

## Make Grape with Plotly

```bash
import plotly.express as px
import chart_studio

gapminder = px.data.gapminder()
fig = px.scatter(gapminder.query("year==2007"), x="gdpPercap", y="lifeExp", size="pop", color="continent",
           hover_name="country", log_x=True, size_max=60)
fig.show()
```

{% iframe https://plotly.com/~jhm0614/1 %}

```bash
import plotly.express as px
import chart_studio
df = px.data.gapminder().query("year == 2007").query("continent == 'Europe'")
df.loc[df['pop'] < 2.e6, 'country'] = 'Other countries'
fig = px.pie(df, values='pop', names='country', title='Population of European continent')
fig.show()
```
{% iframe https://plotly.com/~jhm0614/3 %}

```bash
import plotly.graph_objects as go
fig = go.Figure(
    data=[go.Bar(y=[2, 1, 3])],
    layout_title_text="A Figure Displayed with fig.show()"
)
fig.show()
```
{% iframe https://plotly.com/~jhm0614/5 %}

```bash
import plotly.graph_objects as go
from plotly.subplots import make_subplots

fig = make_subplots(specs=[[{"secondary_y": True}]])

fig.add_trace(
    go.Scatter(x=[1, 2, 3], y=[40, 50, 60], name="yaxis data"),
    secondary_y=True,
)

fig.add_trace(
    go.Scatter(x=[2, 3, 4], y=[40, 50, 60], name="yaxis2 data"),
    secondary_y=True,
)
fig.update_layout(
    title_text="Double Y Axis Example"
)

fig.update_xaxes(title_text="xaxis title")

fig.update_yaxes(title_text="<b>primary</b> yaxis title", secondary_y=False)
fig.update_yaxes(title_text="<b>secondary</b> yaxis title", secondary_y=True)

fig.show()
```

{% iframe https://plotly.com/~jhm0614/7 %}

```bash
#graph example

import plotly.graph_objects as go
from plotly.subplots import make_subplots

fig = make_subplots(rows=2, cols=2,
                     specs=[[{"secondary_y": True}, {"secondary_y": True}],
                            [{"secondary_y": True}, {"secondary_y": True}]])
fig.update_layout(
    title_text="Multiple Y-Axes Subplots"
)
# Top left
fig.add_trace(
    go.Scatter(x=[1, 2, 3], y=[2, 52, 62], name="yaxis data"),
    row=1, col=1, secondary_y=False
)

fig.add_trace(
    go.Scatter(x=[1, 2, 3], y=[40, 50, 60], name="yaxis2 data"),
    row=1, col=1, secondary_y=True,
)

# Top right
fig.add_trace(
    go.Scatter(x=[1, 2, 3], y=[2, 52, 62], name="yaxis3 data"),
    row=1, col=2, secondary_y=False,
)

fig.add_trace(
    go.Scatter(x=[1, 2, 3], y=[40, 50, 60], name="yaxis4 data"),
    row=1, col=2, secondary_y=True,
)

# Bottom left
fig.add_trace(
    go.Scatter(x=[1, 2, 3], y=[2, 52, 62], name='yaxis5 data'),
    row=2, col=1, secondary_y=False,
)

fig.add_trace(
    go.Scatter(x=[1, 2, 3], y=[40, 50, 60], name='yaxis6 data'),
    row=2, col=1, secondary_y=True,
)

# Bottom right
fig.add_trace(
    go.Scatter(x=[1, 2, 3], y=[2, 52, 62], name='yaxis7 data'),
    row=2, col=2, secondary_y=False,
)

fig.add_trace(
    go.Scatter(x=[1, 2, 3], y=[40, 50, 60], name='yaxis8 data'),
    row=2, col=2, secondary_y=True,
)

fig.show()
```
{% iframe https://plotly.com/~jhm0614/9 %}



