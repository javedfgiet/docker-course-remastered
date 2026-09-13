<h1>Running Ruby App in Docker</h1>

<p>This example shows how to run a Ruby script (<code>script.rb</code>) inside a Docker container using the <b>Ruby</b> image.</p>

<h2>🚀 Correct Command</h2>
<pre><code>docker run --rm -v "C:\Users\javed\source\repos\docker-course-remastered\workbook-starter-projects\01-starter-projects\ruby-user-input:/app/" --name ruby-application ruby:3.0.0 ruby /app/script.rb
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
      <li>Maps your local folder (<code>ruby-user-input</code>) to <code>/app</code> inside the container.</li>
      <li>This makes <code>script.rb</code> available to the container.</li>
    </ul>
  </li>
  <li><b>Container name</b>
    <ul>
      <li><code>--name ruby-application</code> assigns a custom name to the container.</li>
    </ul>
  </li>
  <li><b>Image</b>
    <ul>
      <li>Uses <code>ruby:3.0.0</code> as the base image.</li>
    </ul>
  </li>
  <li><b>Script execution</b>
    <ul>
      <li>Runs the Ruby script with:
        <pre><code>ruby /app/script.rb</code></pre>
      </li>
    </ul>
  </li>
</ol>

<h2>📊 Example Output</h2>
<pre><code>+--------------------------------------------------------------------------+
| Strive not to be a success, but rather to be of value. - Albert Einstein |
+--------------------------------------------------------------------------+
</code></pre>

<h2>✅ Summary</h2>
<p>By mounting the project folder, naming the container, and specifying the correct script path, you can run your Ruby application seamlessly inside Docker.</p>
