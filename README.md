
# *Title: Unleashing the Power of Streamlit: A Comprehensive Guide with Examples*

Streamlit is a powerful open-source Python library that revolutionizes the way you build and share data apps. With its intuitive API and rich set of features, Streamlit empowers developers to create interactive, visually stunning applications with minimal effort. In this comprehensive guide, we'll explore the vast capabilities of Streamlit, complete with practical examples to help you unlock its full potential.

**Getting Started**

1. Install Streamlit by running `pip install streamlit` in your terminal or command prompt.
2. Import Streamlit in your Python script using `import streamlit as st`.

```python
pip install streamlit
import streamlit as st
```

**Displaying Text and Widgets**

Streamlit provides several functions to display text, markdown, LaTeX, and interactive widgets:

- `st.text('Fixed width text')`: Display fixed-width text.
- `st.markdown('_Markdown_')`: Display markdown-formatted text.
- `st.caption('Balloons. Hundreds of them...')`: Display a caption.
- `st.latex(r''' e^{i\pi} + 1 = 0 ''')`: Display mathematical expressions using LaTeX.
- `st.button('Hit me')`: Display a button.
- `st.checkbox('Check me out')`: Display a checkbox.
- `st.radio('Pick one:', ['nose','ear'])`: Display a radio button.
- `st.selectbox('Select', [1,2,3])`: Display a select box.
- `st.multiselect('Multiselect', [1,2,3])`: Display a multi-select widget.

**Displaying Data**

Streamlit makes it easy to display various data formats:

- `st.dataframe(my_dataframe)`: Display a pandas DataFrame.
- `st.table(data.iloc[0:10])`: Display a table with data.
- `st.json({'foo':'bar','fu':'ba'})`: Display JSON data.
- `st.metric(label="Temp", value="273 K", delta="1.2 K")`: Display a metric with a label, value, and delta.

**Displaying Media**

You can display images, audio, and video using the following functions:

- `st.image('./header.png')`: Display an image.
- `st.audio(data)`: Display audio data.
- `st.video(data)`: Display video data.

**Layout and Containers**

Streamlit provides options for organizing your app's layout:

- `col1, col2 = st.columns(2)`: Create two columns.
- `with col1: st.write('Column 1')`: Write content in a specific column.
- `tab1, tab2 = st.tabs(["Tab 1", "Tab2"])`: Create tabs.
- `with tab1: st.write("this is tab 1")`: Write content in a specific tab.

**Caching and Performance**

Streamlit offers caching mechanisms to optimize performance:

- `@st.cache_data`: Cache data objects like DataFrames or downloaded data.
- `@st.cache_resource`: Cache global resources like TensorFlow sessions or database connections.

**Control Flow and User Personalization**

Streamlit allows you to control the flow of your app and personalize it for users:

- `st.stop()`: Stop execution immediately.
- `st.experimental_rerun()`: Rerun the script immediately.
- `with st.form(key='my_form'): ...`: Group multiple widgets in a form.
- `if st.user.email == 'jane@email.com': ...`: Show different content based on the user's email.

**Additional Features**

The cheat sheet also covers:

- Displaying code with `st.echo()`.
- Placeholders with `st.empty()` and `st.container()`.
- Displaying help and options with `st.help()`, `st.get_option()`, and `st.set_option()`.
- Configuring the page layout with `st.set_page_config()`.
- Displaying progress and status with `st.spinner()`, `st.progress()`, and various status messages like `st.success()`, `st.warning()`, and `st.error()`.
- Displaying visual effects like `st.balloons()` and `st.snow()`.

The cheat sheet also covers a few other useful features and capabilities in Streamlit:

**Connecting to Data Sources**

Streamlit provides an experimental function to connect to different data sources:

- `st.experimental_connection('pets_db', type='sql')`: Connect to a SQL database.
- `conn = st.experimental_connection('sql')`: Connect to a SQL database and store the connection object.
- `conn = st.experimental_connection('snowpark')`: Connect to a Snowpark session.

**Magic Commands**

Streamlit supports "magic commands" which are special strings that allow you to display or execute code inline:

- `st.write('_This_ is some __Markdown__')`: Write markdown formatted text.
- `st.write('dataframe:', data)`: Display a data object like a DataFrame.
- `a=3`: Execute a Python statement.

**Command Line Interface**

Streamlit provides a command line interface with several useful commands:

- `streamlit run your_script.py`: Run a Streamlit script.
- `streamlit hello`: Run the "Hello" example script.
- `streamlit config show`: Show the current config settings.
- `streamlit cache clear`: Clear the cache.
- `streamlit docs`: Open the documentation in a browser.
- `streamlit --version`: Show the installed Streamlit version.

**Pre-Release Features**

The cheat sheet mentions a few pre-release or experimental features:

- `st.experimental_show(objects)`: Display objects in an experimental way.
- `st.experimental_get_query_params()`: Get query parameters from the URL.
- `st.experimental_set_query_params(**params)`: Set query parameters in the URL.

**Deprecated Caching**

The deprecated `@st.cache` decorator for caching functions, which has been replaced by `@st.cache_data` and `@st.cache_resource`.

Sure, here are example code snippets for each of the additional topics covered in the Streamlit cheat sheet:

**Connecting to Data Sources**:
```python
# Connect to a SQL database
st.experimental_connection('pets_db', type='sql')

# Connect to a SQL database and store connection
conn = st.experimental_connection('sql')

# Connect to a Snowpark session
conn = st.experimental_connection('snowpark')
```

**Magic Commands**:
```python
# Write markdown formatted text
st.write('_This_ is some __Markdown__')

# Display a data object like a DataFrame
st.write('dataframe:', data)

# Execute a Python statement
a = 3
```

**Command Line Interface**:
```bash
# Run a Streamlit script
$ streamlit run your_script.py

# Run the "Hello" example script
$ streamlit hello

# Show current config settings  
$ streamlit config show

# Clear the cache
$ streamlit cache clear

# Open the documentation in a browser
$ streamlit docs

# Show installed Streamlit version
$ streamlit --version
```

**Pre-Release Features**:
```python
# Display objects in an experimental way
st.experimental_show(objects)

# Get query parameters from the URL
query_params = st.experimental_get_query_params()

# Set query parameters in the URL
st.experimental_set_query_params(param1="value1", param2="value2")
```

**Deprecated Caching**:
```python
# Deprecated caching function
@st.cache
def foo(bar):
    # Do something expensive in here...
    return data

# Executes foo
d1 = foo(ref1)

# Does not execute foo, returns cached item by reference
d2 = foo(ref1)

# Different arg, so function foo executes
d3 = foo(ref2)
```


**Sidebar Widgets**:
```python
# Add a radio button to the sidebar
a = st.sidebar.radio('Choose one:', ['option1', 'option2'])

# Add other widgets to the sidebar
st.sidebar.button('Click me')
st.sidebar.checkbox('Check this')
st.sidebar.selectbox('Pick an option', ['a', 'b', 'c'])
```

**Displaying Chat Applications**:
```python
# Insert a chat message container
with st.chat_message("user"):
    st.write("Hello 👋")
    st.line_chart(np.random.randn(30, 3))

# Display a chat input widget
user_input = st.chat_input("Say something")
```

**Mutating Data**:
```python
# Add rows to a dataframe after displaying it
element = st.dataframe(df1)
element.add_rows(df2)

# Add rows to a chart after displaying it
element = st.line_chart(df1)
element.add_rows(df2)
```

**Personalize Apps for Users**:
```python
# Show different content based on user's email
if st.user.email == 'jane@email.com':
    display_jane_content()
elif st.user.email == 'adam@foocorp.io':
    display_adam_content()
else:
    st.write("Please contact us to get access!")
```

**Display Code**:
```python
# Display and execute code
st.echo()
with st.echo():
    st.write('Code will be executed and printed')
```

**Placeholders and Containers**:
```python
# Replace any single element
element = st.empty()
element.line_chart(...)
element.text_input(...) # Replaces previous

# Insert out of order
elements = st.container()
elements.line_chart(...)
st.write("Hello")
elements.text_input(...) # Appears above "Hello"
```

**Help and Options**:
```python
# Get help for a Python object
st.help(pandas.DataFrame)

# Get an option value
option_value = st.get_option('option_key')

# Set an option value
st.set_option('option_key', 'new_value')
```


**Control Flow**:
```python
# Stop execution immediately
st.stop()

# Rerun script immediately 
st.experimental_rerun()

# Group multiple widgets in a form
with st.form(key='my_form'):
    username = st.text_input('Username')
    password = st.text_input('Password')
    submitted = st.form_submit_button('Login')
    if submitted:
        # Process login credentials
        ...
```

**Displaying Progress and Status**:
```python
# Show a spinner during a process
with st.spinner('Processing data...'):
    time.sleep(5) # Simulate some work
    st.success('Data processed successfully!')

# Show and update a progress bar
progress_bar = st.progress(0)
for i in range(100):
    time.sleep(0.1)
    progress_bar.progress(i + 1)

# Display various status messages
st.error('An error occurred!')
st.warning('Warning: data may be incomplete')
st.info('Here is some information')
```

**Visual Effects**:
```python
# Display balloons animation
st.balloons()

# Display snow animation
st.snow()

# Display a toast message
st.toast('Mr Stay-Puft is here!')
```

**Page Configuration**:
```python
# Set page layout to wide mode
st.set_page_config(layout='wide')

# Set page title and icon
st.set_page_config(page_title='My App', page_icon='🚀')
```

**Experimental Features**:
```python
# Get query parameters from URL
query_params = st.experimental_get_query_params()
param1 = query_params.get('param1', 'default_value')

# Set query parameters in URL
st.experimental_set_query_params(param1='value1', param2='value2')
```


**Columns and Layouts**:
```python
# Create two equal columns
col1, col2 = st.columns(2)

# Create columns with different widths
col1, col2, col3 = st.columns([3, 1, 1])

# Add content to columns
with col1:
    st.header("Column 1")
    st.write("This is column 1 content.")

with col2:
    st.header("Column 2")
    st.write("This is column 2 content.")
```

**File Uploads and Downloads**:
```python
# File uploader
uploaded_file = st.file_uploader("Choose a file")
if uploaded_file is not None:
    # Process the uploaded file
    ...

# Download button
@st.cache_data
def load_data():
    # Load or generate data
    return data

data = load_data()

st.download_button(
    "Download data",
    data.to_csv().encode('utf-8'),
    file_name="data.csv",
    mime="text/csv",
)
```

**Camera Input**:
```python
# Get camera input
camera_input = st.camera_input("Take a picture")

if camera_input:
    # Process the camera input (image)
    ...
```

**Color Picker**:
```python
# Color picker
color = st.color_picker('Pick a color', '#00ff00')
st.write(f'The selected color is {color}')
```

**Data Editor**:
```python
# Data editor
data = st.data_editor(
    'Edit data',
    {
        'firstName': ['John', 'Jane'],
        'lastName': ['Doe', 'Doe'],
        'age': [25, 30]
    }
)

# Display the edited data
st.dataframe(data)
```

**Custom Components**:
```python
# Define a custom Streamlit component
import streamlit.components.v1 as components

# Load the component's HTML/CSS/JS bundle 
components.html(
    """
    <script src="https://cdn.jsdelivr.net/npm/vue@2.6.14/dist/vue.js"></script>
    <div id="app">
      <p>{{ greeting }} World!</p>
      <input v-model="greeting" placeholder="Enter a greeting">
    </div>
    <script>
      var app = new Vue({
        el: '#app',
        data: {
          greeting: 'Hello'
        }
      })
    </script>
    """,
    height=200,
)
```

**Database Connections**:
```python
# Define a custom database connection
import streamlit.experimental_connection as stx

class MyConnection(stx.ExperimentalBaseConnection[MyConnectionType]):
    def _connect(self, **kwargs) -> MyConnectionType:
        # Connect to the database
        return myconn.connect(**self._secrets, **kwargs)

    def query(self, query):
        # Run a database query
        return self._instance.query(query)

# Use the custom connection
conn = st.experimental_connection("myconn", MyConnection)
result = conn.query("SELECT * FROM mytable")
st.dataframe(result)
```

**Background Tasks**:
```python
# Run a background task
task = st.background_task("Background Task", long_running_function)
while not task.is_completed:
    st.progress(task.progress_value)
    time.sleep(1)

# Get the result from the background task
result = task.output
```

**File Transfer**:
```python
# Upload a file
uploaded_file = st.file_uploader("Choose a file")
if uploaded_file:
    # Process the uploaded file
    ...

# Download a file
if st.download_button("Download File", data, file_name="data.txt"):
    # File was downloaded
    ...
```

**Context Managers**:
```python
# Use a context manager
with st.spinner("Loading..."):
    time.sleep(2)
    st.success("Data loaded!")

with st.expander("Show details"):
    st.write("Here are the details...")
```

**State Management**:
```python
# Use session state to manage state across reruns
if "count" not in st.session_state:
    st.session_state.count = 0

increment = st.button("Increment")
if increment:
    st.session_state.count += 1

st.write(f"Count: {st.session_state.count}")
```

**Caching Functions**:
```python
# Cache a function based on input parameters
@st.cache_data()
def expensive_computation(a, b):
    # Perform some expensive computation
    return result

a = st.number_input("Enter a", value=1)
b = st.number_input("Enter b", value=2)

# Calling the cached function
result = expensive_computation(a, b)
st.write(f"Result: {result}")
```

**Theming**:
```python
# Set a primary color for the theme
st.set_option('primary_color', '#3EB489')

# Set a custom theme
theme = {
    "primaryColor": "#3EB489",
    "backgroundColor": "#F5F5F5",
    "secondaryBackgroundColor": "#D6F3E5",
    "textColor": "#262730",
    "font": "monospace"
}
st.set_option('theme', theme)
```

**Accessibility**:
```python
# Set the page icon and title for accessibility
st.set_page_config(page_title="My App", page_icon=":rocket:")

# Add alt text to an image for screen readers
st.image("logo.png", caption="Company Logo", use_column_width=True)

# Add tooltips and keyboard shortcuts
help_tooltip = """
This is a tooltip that explains what this section is about.

Keyboard shortcut: Ctrl + Q
"""
st.tooltip(help_tooltip)
```

**Inserting HTML**:
```python
# Insert HTML code directly
st.markdown(
    """
    <style>
    .custom-css-class {
        color: red;
        font-weight: bold;
    }
    </style>
    <div class="custom-css-class">This text is styled with CSS</div>
    """,
    unsafe_allow_html=True
)
```


**Reactive Updates**:
```python
# Create a text input widget
text_input = st.text_input("Enter some text")

# Reactively update content based on user input
if text_input:
    st.write(f"You entered: {text_input}")
    # Perform further operations based on user input
```

**Handling Events**:
```python
# Create a button
if st.button("Click me"):
    # Perform an action when the button is clicked
    st.write("Button clicked!")

# Capture key events
key = st.text_input("Press any key", max_chars=1)
if key:
    st.write(f"You pressed: {key}")
```

**Deployment**:
```python
# Deploy your Streamlit app to a cloud service
# For example, with Streamlit Sharing:
$ streamlit deploy --serverless

# For other deployment options, refer to the Streamlit docs
```

**Logging and Debugging**:
```python
import streamlit as st
import logging

# Set up logging
logging.basicConfig(level=logging.DEBUG)

st.write("This is a Streamlit app.")

# Log messages for debugging
logging.debug("This is a debug message.")
logging.info("This is an info message.")
logging.warning("This is a warning message.")
logging.error("This is an error message.")
```

**Performance Optimization**:
```python
# Cache expensive computations
@st.cache_data
def expensive_computation(arg1, arg2):
    # Perform expensive computation
    return result

# Use context managers for efficient resource management
with open("data.txt", "r") as f:
    data = f.read()

# Avoid redundant computations and redraws
if st.checkbox("Perform computation"):
    result = expensive_computation(arg1, arg2)
    st.write(result)
```

**Testing and Debugging**:
```python
# Run Streamlit in test mode
$ streamlit run your_script.py --server.headless=true

# Use the st.pprint() function for pretty-printing objects
st.pprint(data)

# Leverage the st.stop() function for debugging
if some_condition:
    st.stop()
```


**Interactive Visualizations**:
```python
# Interactive matplotlib plot
import matplotlib.pyplot as plt
import numpy as np

fig, ax = plt.subplots()
data = np.random.randn(100, 2)
ax.scatter(data[:, 0], data[:, 1])

# Use st.pyplot() to display the plot
st.pyplot(fig)

# Interactive plotly chart
import plotly.express as px

df = px.data.iris()
fig = px.scatter(df, x="sepal_width", y="sepal_length", color="species")

# Use st.plotly_chart() to display the chart
st.plotly_chart(fig)
```

**Dynamic Content Generation**:
```python
# Generate content dynamically based on user input
options = st.multiselect("Select options", ["Option 1", "Option 2", "Option 3"])

if options:
    for option in options:
        st.write(f"You selected: {option}")
        # Generate dynamic content based on the selected option
```

**Conditional Rendering**:
```python
# Conditionally render content based on user input
show_content = st.checkbox("Show content")

if show_content:
    st.write("This content is shown when the checkbox is checked.")
else:
    st.write("This content is shown when the checkbox is unchecked.")
```

**Animations**:
```python
# Create an animation with Streamlit elements
import time

progress_bar = st.progress(0)
status_text = st.empty()

for i in range(101):
    status_text.text(f"Processing: {i}%")
    progress_bar.progress(i)
    time.sleep(0.05)

status_text.text("Processing complete!")
```

**Internationalisation (i18n)**:
```python
# Translate text using i18n
import streamlit as st
from streamlit.translation import TranslationContext

with TranslationContext("es"):  # Spanish
    st.write("¡Hola, mundo!")

with TranslationContext("fr"):  # French
    st.write("Bonjour le monde!")
```


**Loading and Caching External Data**:
```python
import pandas as pd

# Load data from a URL
@st.cache_data
def load_data(url):
    return pd.read_csv(url)

url = st.text_input("Enter a URL to load data")
if url:
    data = load_data(url)
    st.dataframe(data)
```

**Interactive Maps**:
```python
import streamlit as st
import pydeck as pdk

# Load data
data = pd.read_json("data.json")

# Create a pydeck view
view = pdk.data_utils.compute_view(data[["lon", "lat"]])
view.pitch = 75

# Create a pydeck layer
layer = pdk.Layer(
    "ScatterplotLayer",
    data=data,
    get_position=["lon", "lat"],
    get_radius=100,
    get_fill_color=[180, 0, 200, 140],
)

# Display the map
r = pdk.Deck(layers=[layer], initial_view_state=view, mapbox_key=st.secrets["mapbox_key"])
st.pydeck_chart(r)
```

**Callbacks and Crosstalk**:
```python
import streamlit as st
from streamlit_observable import observable

# Define a callback function
@observable
def on_value_change(this, old_value, new_value):
    st.write(f"Value changed from {old_value} to {new_value}")

# Create an input widget
value = st.number_input("Enter a number", on_change=on_value_change)

# Trigger the callback
on_value_change(None, None, value)
```

**WebSockets and Streaming**:
```python
import streamlit as st
import asyncio

# Define a function to stream data
async def stream_data():
    for i in range(10):
        await asyncio.sleep(1)
        yield i

# Create a Streamlit app
def app():
    data_stream = st.experimental_data_stream(stream_data())
    for value in data_stream:
        st.write(f"Received: {value}")

# Run the app
app()
```

**Streamlit Components**:
```python
import streamlit as st
from streamlit.components.v1 import html

# Define a custom HTML component
html_component = html(
    """
    <script>
        const sendMessage = () => {
            const message = document.getElementById("message").value;
            Streamlit.setComponentValue(message);
        };
    </script>
    <input id="message" type="text" placeholder="Enter a message">
    <button onclick="sendMessage()">Send</button>
    """,
    height=100,
)

# Receive the message
message = html_component.get_value()
st.write(f"Received message: {message}")
```


This comprehensive guide has covered the essentials of building powerful data apps with Streamlit, complete with practical examples to help you unlock its full potential. Whether you're a seasoned developer or just starting out, Streamlit empowers you to create stunning, interactive applications with ease. Dive in, experiment, and unleash the full power of this remarkable library!
