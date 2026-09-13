<h1>Running Python Script in Docker</h1>

<p>This example shows how to run a Python script (<code>script.py</code>) inside a Docker container using the <b>Python</b> image, while passing command-line arguments.</p>

<h2>🚀 Correct Command</h2>
<pre><code>docker run --rm -v "C:\Users\javed\source\repos\docker-course-remastered\workbook-starter-projects\01-starter-projects\python-script:/app/" --name python-script-container python:3.8-slim python /app/script.py Hello From Docker
</code></pre>

<h2>⚠️ Key Points</h2>
<ol>
  <li><b>--rm flag</b>
    <ul>
      <li>Ensures the container is removed after execution.</li>
    </ul>
  </li>
  <li><b>Volume mount</b>
    <ul>
      <li>Maps your local folder (<code>python-script</code>) to <code>/app</code> inside the container.</li>
      <li>This makes <code>script.py</code> available to the container.</li>
    </ul>
  </li>
  <li><b>Container name</b>
    <ul>
      <li><code>--name python-script-container</code> assigns a custom name to the container.</li>
    </ul>
  </li>
  <li><b>Image</b>
    <ul>
      <li>Uses <code>python:3.8-slim</code> as the base image.</li>
    </ul>
  </li>
  <li><b>Script execution with arguments</b>
    <ul>
      <li>Runs the Python script with:
        <pre><code>python /app/script.py Hello From Docker</code></pre>
      </li>
      <li>Arguments <code>Hello From Docker</code> are passed to the script.</li>
    </ul>
  </li>
</ol>

<h2>📊 Example Output</h2>
<pre><code>Command-line arguments:
Hello
From
Docker
</code></pre>

<h2>✅ Summary</h2>
<p>By mounting the project folder, naming the container, and specifying the correct script path, you can run your Python application seamlessly inside Docker and pass command-line arguments to it.</p>
