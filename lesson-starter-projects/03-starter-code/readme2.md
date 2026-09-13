<h1>Exploring Python App Container</h1>

<p>This example shows how to start an interactive shell inside a Python container built from the <code>python-app</code> image and inspect its contents.</p>

<h2>🚀 Run Command</h2>
<pre><code>docker run -it --rm --name python-app-container python-app /bin/sh
</code></pre>

<h2>📊 Example Session</h2>
<pre><code># ls
python-app.py
# exit
</code></pre>

<h2>⚠️ Key Points</h2>
<ol>
  <li><b>-it flags</b>
    <ul>
      <li><code>-i</code> keeps STDIN open.</li>
      <li><code>-t</code> allocates a pseudo-TTY for interactive shell access.</li>
    </ul>
  </li>
  <li><b>--rm flag</b>
    <ul>
      <li>Ensures the container is removed after you exit.</li>
    </ul>
  </li>
  <li><b>Container name</b>
    <ul>
      <li><code>--name python-app-container</code> assigns a custom name to the container.</li>
    </ul>
  </li>
  <li><b>Shell access</b>
    <ul>
      <li><code>/bin/sh</code> starts a shell inside the container.</li>
      <li>You can run commands like <code>ls</code> to inspect files.</li>
    </ul>
  </li>
</ol>

<h2>✅ Summary</h2>
<p>By running the container interactively with <code>/bin/sh</code>, you can explore the filesystem, verify that <code>python-app.py</code> was copied correctly, and debug issues directly inside the container.</p>
