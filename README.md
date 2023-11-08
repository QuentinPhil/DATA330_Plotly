# DATA330_Plotly

'''{python}
import pandas as pd
import numpy as np
import plotly
import plotly.graph_objects as go
from plotly.subplots import make_subplots

import plotly.io as pio
pio.renderers.default = 'notebook'

df1 = pd.read_csv("Canada_2021_popn.csv")

df1.head()

df2 = pd.melt(df1,id_vars=['Location'], value_vars=['First_Nations','Inuit','Métis','Non_Indigenous'])
import plotly.offline as pyo
pyo.init_notebook_mode(connected=True)

fig = make_subplots(rows=1, cols=1, specs=[[{'type':'domain'}]])
labels = ["First Nations","Intuit","Métis", "Non Indigenous"]
fig.add_trace(go.Pie(labels=labels,values = a, name = "Population Chart",textinfo="label+percent",
                    insidetextorientation="horizontal",textposition="outside",
                    marker = dict(colors=colors1)),1,1)

fig.update_layout(showlegend=False,title_text="Indigenous Population In Canada", 
                 annotations = [dict(text="Canda", x=.5, y=.6, font_size=20, showarrow=False),
                               dict(text="Total Population:",x=.5, y=.5, font_size=20,showarrow=False),
                               dict(text="38.5 Million",x=.5,y=.4,font_size=20,showarrow=False)])

fig.update_traces(hole=.6, hoverinfo="label+value",hoverlabel = dict(font_color=["white","white","black","white"],
                            font_size=18))

fig.show()


'''
###Checking if website is being hosted


