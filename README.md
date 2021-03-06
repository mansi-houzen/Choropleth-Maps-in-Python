# Choropleth Maps in Python
 Usage of plotly and cufflinks for plotting Choropleth plots

## Choropleth Maps - Summary
### Step 1: Imports and Set-up - plotly and cufflinks
USE 4 FOR PLOTLY, 2 FOR CUFFLINKS OR COPY/PASTE
from plotly.offline import download_plotlyjs, init_notebook_mode, plot, iplot

import chart_studio.plotly as py

init_notebook_mode(connected=True)

import plotly.graph_objs as go

import cufflinks as cf

cf.go_offline()

USE THE PLOTLY CHEAT SHEET

### Step 2: 2 main objects - data and layout
Step 2.1: data dict() object
Now we need to begin to build our data dictionary. Easiest way to do this is to use the dict() function of the general form:

type = 'choropleth',
locations = list of abbreviation codes of states
locationmode = 'USA-states'
colorscale=
Either a predefined string:

'pairs' | 'Greys' | 'Greens' | 'Bluered' | 'Hot' | 'Picnic' | 'Portland' | 'Jet' | 'RdBu' | 'Blackbody' | 'Earth' | 'Electric' | 'YIOrRd' | 'YIGnBu'
or create a custom colorscale

text= list or array of text to display corresponding to locations
z= array of values on z axis (color of state)
colorbar = {'title':'Colorbar Title here'})
Step 2.2: Layout dict() object
Then we create the layout nested dictionary: geo is one key which has another dictionary as value. Nested dict has 'scope' as key and usa as value

layout = dict(geo = {'scope':'usa'})
### Step 3: Using go.figure() Set up the object that finally gets passed into iplot()
Then we use:

choromap = go.Figure(data = [data],layout = layout)

### Step 4: plot the choromap
iplot(choromap) within the jupyter notebook
plot(choromap) to open choromap s an HTML file outside the NB in the browser
USA vs WORLD
change in key,value pairs of data and layout dictionaries below
