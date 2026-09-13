<h1>Running Python App in Docker</h1>

<p>This guide explains how to correctly run a Python script inside a Docker container on Windows using volume mounts.</p>

<h2>🚀 Correct Command</h2>
<pre><code>docker run --rm -v "C:\Users\javed\source\repos\docker-course-remastered\lesson-starter-projects\01-starter-code:/app" --name pythonTest python:3.8-slim python /app/python-app.py
</code></pre>

<h2>⚠️ Common Issues and Fixes</h2>
<ol>
  <li><b>Order of flags</b>
    <ul>
      <li><code>--rm</code> must come right after <code>docker run</code>.</li>
      <li><code>--name</code> must be placed before the image name, not after the command.</li>
    </ul>
  </li>
  <li><b>Volume mount syntax</b>
    <ul>
      <li>Windows paths need quotes and proper escaping.</li>
      <li>Correct form:
        <pre><code>-v "C:\path\to\folder:/app"</code></pre>
      </li>
    </ul>
  </li>
  <li><b>Container name placement</b>
    <ul>
      <li><code>--name pythonTest</code> should be specified before the image (<code>python:3.8-slim</code>).</li>
    </ul>
  </li>
  <li><b>Script path inside container</b>
    <ul>
      <li>You mounted your local folder to <code>/app</code>.</li>
      <li>Therefore, the script should be referenced as:
        <pre><code>python /app/python-app.py</code></pre>
        <p><b>Not</b> <code>app/python-app.py</code>.</p>
      </li>
    </ul>
  </li>
</ol>

<h2>✅ Summary</h2>
<p>By fixing the flag order, mount syntax, container name placement, and script path, you ensure Docker runs your Python app correctly inside the container.</p>
