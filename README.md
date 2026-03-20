<!DOCTYPE html>
<html>
<body>

  <h1>Parti Live Stream API Documentation</h1>

  <p>
    This documentation provides details for interacting with the <b>Parti.com Livestream Channel Info API</b>. Use these endpoints to retrieve real-time data about active streamers, viewer counts, and playback URLs.
  </p>

  <hr />

  <h2>1. Authentication</h2>
  <p>All requests require a Bearer Token provided in the Authorization header.</p>
  <pre style="background-color: #f4f4f4; padding: 10px; border-radius: 5px;">
<strong>Header:</strong> Authorization
<strong>Value:</strong> Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzUxMiJ9... (truncated)</pre>

  <hr />

  <h2>2. Endpoints</h2>

  <h3>Get Active Livestreams</h3>
  <p>Retrieves a list of channels currently broadcasting live.</p>

  <table border="1" style="width:100%; border-collapse: collapse; text-align: left;">
    <tr style="background-color: #e0e0e0;">
      <th style="padding: 10px;">Method</th>
      <th style="padding: 10px;">URL</th>
      <th style="padding: 10px;">Parameters</th>
    </tr>
    <tr>
      <td style="padding: 10px;"><code>GET</code></td>
      <td style="padding: 10px;"><code>https://prod-api.parti.com/parti_v2/profile/get_livestream_channel_info/live</code></td>
      <td style="padding: 10px;">
        <code>limit</code>: Result count (e.g., 30, 100)<br>
        <code>offset</code>: Pagination start point
      </td>
    </tr>
  </table>

  <hr />

  <h2>3. Data Schema</h2>
  <p>The API returns an array of objects representing active streams. Key fields include:</p>

  <ul>
    <li><strong>user_name:</strong> The display name of the streamer.</li>
    <li><strong>event_title:</strong> The current title of the live broadcast.</li>
    <li><strong>viewers_count:</strong> Real-time number of current viewers.</li>
    <li><strong>playback_url:</strong> The HLS (.m3u8) stream link for playback.</li>
    <li><strong>event_file:</strong> A URL to the most recent stream screenshot/thumbnail.</li>
  </ul>

  <hr />

  <h2>4. Sample Response</h2>
  <pre style="background-color: #2d2d2d; color: #cccccc; padding: 15px; border-radius: 5px; overflow-x: auto;">
[
  {
    "user_id": 664217,
    "user_name": "KristosCast",
    "event_title": "I'm Live on Parti",
    "category_name": "Other",
    "viewers_count": 7,
    "playback_url": "https://media.parti.com/.../main.m3u8"
  }
]</pre>

  <hr />

  <h2>5. Development Context</h2>
  <p>
    This API is compatible with <b>Node.js</b> automation tools. For developers using <b>Puppeteer</b> or custom mirroring bots, use the <code>playback_url</code> for archiving or <code>event_file</code> for generating live previews in external dashboards.
  </p>

</body>
</html>
