<h1>Running Full Grade Submission Application in Docker</h1>

<p>This example shows how to run a complete application where users can submit details on a portal (frontend Flask app) and it connects to a backend Node.js grade service via a Docker network.</p>

<h2>🔗 Create a Docker Network</h2>
<pre><code>docker network create my-network
</code></pre>

<h2>🚀 Run Backend (Grade Submission API)</h2>
<pre><code>docker run --name node-server --network my-network --rm -p 3000:3000 javedfgiet/grade-submision-api
</code></pre>

<h3>📊 Example Output</h3>
<pre><code>Grade service is running on port 3000
Received POST request, added new grade: { id: '1789316618278', name: 'Javed', subject: 'Maths', score: '800' }
Received GET request for grades
</code></pre>

<h2>🚀 Run Frontend (Grade Submission Portal)</h2>
<pre><code>docker run --name flask-app --network my-network --rm -p 5000:5001 -e GRADE_SERVICE_HOST=node-server javedfgiet/grade-submission-portal
</code></pre>

<h3>📊 Example Output</h3>
<pre><code> * Serving Flask app 'app' (lazy loading)
 * Environment: production
 * Debug mode: on
 * Running on http://172.18.0.3:5001/ (Press CTRL+C to quit)
172.18.0.1 - - [13/Sep/2026 16:23:19] "GET / HTTP/1.1" 200 -
172.18.0.1 - - [13/Sep/2026 16:23:38] "POST /handleSubmit HTTP/1.1" 302 -
172.18.0.1 - - [13/Sep/2026 16:23:38] "GET /grades HTTP/1.1" 200 -
172.18.0.1 - - [13/Sep/2026 16:23:38] "GET /api/grades HTTP/1.1" 200 -
</code></pre>

<h2>🌐 Access in Browser</h2>
<p>Since the Flask portal runs on <code>5001</code> inside the container and is mapped to <code>5000</code> on your host machine, open:</p>
<pre><code>http://localhost:5000/
</code></pre>

<h2>⚠️ Key Points</h2>
<ol>
  <li><b>Network</b>
    <ul>
      <li>Both containers are attached to <code>my-network</code> so they can resolve each other by name.</li>
      <li>The Flask app uses <code>GRADE_SERVICE_HOST=node-server</code> to connect to the backend.</li>
    </ul>
  </li>
  <li><b>Backend</b>
    <ul>
      <li>Runs on port <code>3000</code> inside the container, mapped to <code>3000</code> on the host.</li>
    </ul>
  </li>
  <li><b>Frontend</b>
    <ul>
      <li>Runs on port <code>5001</code> inside the container, mapped to <code>5000</code> on the host.</li>
      <li>Handles form submissions and fetches grades from the backend API.</li>
    </ul>
  </li>
</ol>

<h2>✅ Summary</h2>
<p>By creating a Docker network and running both the Flask frontend and Node.js backend containers on it, you can deploy a fully functional Grade Submission application. The frontend portal allows users to submit details, while the backend service stores and retrieves grades.</p>
