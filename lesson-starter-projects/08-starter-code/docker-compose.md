<h1>Running Grade Submission Application with Docker Compose</h1>

<p>This example shows how to run the full Grade Submission application (Flask portal + Node.js API) using <b>docker-compose</b>.</p>

<h2>📄 docker-compose.yml</h2>
<pre><code>version: "3.8"

services:
  node-server:
    image: javedfgiet/grade-submission-api:latest
    container_name: node-server
    ports:
      - "3000:3000"

  flask-app:
    image: javedfgiet/grade-submission-portal:latest
    container_name: flask-app
    ports:
      - "5000:5001"
    environment:
      - GRADE_SERVICE_HOST=node-server
    depends_on:
      - node-server
</code></pre>

<h2>🚀 Run Application</h2>
<pre><code>docker compose up
</code></pre>

<h2>📊 Example Output</h2>
<pre><code>node-server  | Grade service is running on port 3000
flask-app    |  * Serving Flask app 'app' (lazy loading)
flask-app    |  * Environment: production
flask-app    |  * Debug mode: on
flask-app    |  * Running on http://172.19.0.3:5001/ (Press CTRL+C to quit)
</code></pre>

<h2>🌐 Access in Browser</h2>
<p>Since the Flask portal runs on <code>5001</code> inside the container and is mapped to <code>5000</code> on your host machine, open:</p>
<pre><code>http://localhost:5000/
</code></pre>

<h2>⚠️ Key Points</h2>
<ol>
  <li><b>Compose File</b>
    <ul>
      <li>Defines two services: <code>node-server</code> (backend API) and <code>flask-app</code> (frontend portal).</li>
      <li>Both services share the same default network created by Compose.</li>
    </ul>
  </li>
  <li><b>Environment Variable</b>
    <ul>
      <li><code>GRADE_SERVICE_HOST=node-server</code> tells the Flask app where to find the backend API.</li>
    </ul>
  </li>
  <li><b>Ports</b>
    <ul>
      <li>Backend API → <code>3000</code></li>
      <li>Frontend Portal → <code>5000</code> (mapped from container port <code>5001</code>)</li>
    </ul>
  </li>
</ol>

<h2>✅ Summary</h2>
<p>With <code>docker-compose.yml</code>, you can spin up both the Flask frontend and Node.js backend together with a single command, making deployment and orchestration seamless.</p>
