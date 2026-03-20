<!DOCTYPE html>
<html>
<body style="font-family: sans-serif; line-height: 1.6; color: #333; max-width: 900px; margin: auto; padding: 20px; background-color: #fcfcfc;">

  <h1 style="color: #2c3e50; border-bottom: 2px solid #3498db; padding-bottom: 10px;">Parti Live Stream API Documentation</h1>

  <p>
    This API documentation provides the necessary endpoints for interacting with the <strong>Parti.com</strong> livestreaming platform, covering stream discovery, detailed channel metadata, and moderation.
  </p>

  <hr style="border: 0; height: 1px; background: #eee; margin: 20px 0;" />

  <h2 style="color: #2980b9;">1. Authentication</h2>
  <p>Include the Bearer token in the header of every request. (Token masked for security):</p>
  <div style="background-color: #2d3436; color: #dfe6e9; padding: 15px; border-radius: 4px; font-family: monospace;">
    <strong>Authorization:</strong> Bearer [REDACTED_ACCESS_TOKEN]
  </div>

  <hr style="border: 0; height: 1px; background: #eee; margin: 20px 0;" />

  <h2 style="color: #2980b9;">2. Livestream Endpoints</h2>

  <h3 style="background: #e1e8ed; padding: 8px; border-radius: 4px; border-left: 4px solid #2980b9;">GET /live</h3>
  <p>Fetch a list of all active livestream channels.</p>
  <pre style="background: #fdf6e3; padding: 10px; border: 1px solid #ddd; overflow-x: auto;">GET https://prod-api.parti.com/parti_v2/profile/get_livestream_channel_info/live?limit=30&offset=0</pre>

  <h3 style="background: #e1e8ed; padding: 8px; border-radius: 4px; border-left: 4px solid #2980b9;">GET /get_livestream_channel_info/{id}</h3>
  <p>Retrieve detailed metadata for a specific channel, including RTMP ingest endpoints and event descriptions.</p>
  <pre style="background: #fdf6e3; padding: 10px; border: 1px solid #ddd; overflow-x: auto;">GET https://prod-api.parti.com/parti_v2/profile/get_livestream_channel_info/667897</pre>

  <h3 style="background: #e1e8ed; padding: 8px; border-radius: 4px; border-left: 4px solid #2980b9;">GET /moderators/{id}</h3>
  <p>Fetch the list of moderators for the specified channel ID.</p>
  <pre style="background: #fdf6e3; padding: 10px; border: 1px solid #ddd; overflow-x: auto;">GET https://prod-api.parti.com/parti_v2/profile/livestream/moderators/667897</pre>

  <hr style="border: 0; height: 1px; background: #eee; margin: 20px 0;" />

  <h2 style="color: #2980b9;">3. Data Example: Channel Info</h2>
  <p>Response structure for a specific channel lookup:</p>
  <div style="background: #272822; color: #a6e22e; padding: 15px; border-radius: 5px; font-family: 'Courier New', Courier, monospace; font-size: 0.9em; overflow-x: auto;">
    <pre style="margin: 0;">
{
  "status": "Public",
  "is_moderator": false,
  "channel_info": {
    "channel": {
      "user_id": 667897,
      "ingest_endpoint": "rtmp://stream.parti.com:1935",
      "playback_url": "https://media.parti.com/.../main.m3u8",
      "is_live": true
    },
    "livestream_event_info": {
      "event_name": "I'm Live on Parti",
      "event_description": "Transmisión de los mejores videos musicales..."
    }
  },
  "is_streaming_live_now": true
}
    </pre>
  </div>

  <hr style="border: 0; height: 1px; background: #eee; margin: 20px 0;" />

  <h2 style="color: #2980b9;">4. Global Definitions</h2>
  <table style="width: 100%; border-collapse: collapse; margin-top: 10px; background-color: white;">
    <thead>
      <tr style="background-color: #2980b9; color: white;">
        <th style="padding: 12px; text-align: left; border: 1px solid #ddd;">Key</th>
        <th style="padding: 12px; text-align: left; border: 1px solid #ddd;">Description</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td style="padding: 10px; border: 1px solid #ddd;"><code>ingest_endpoint</code></td>
        <td style="padding: 10px; border: 1px solid #ddd;">RTMP URL for streamers to push content.</td>
      </tr>
      <tr>
        <td style="padding: 10px; border: 1px solid #ddd;"><code>playback_url</code></td>
        <td style="padding: 10px; border: 1px solid #ddd;">The HLS master playlist URL (.m3u8).</td>
      </tr>
      <tr>
        <td style="padding: 10px; border: 1px solid #ddd;"><code>is_moderator</code></td>
        <td style="padding: 10px; border: 1px solid #ddd;">Boolean indicating if the requester has mod privileges.</td>
      </tr>
    </tbody>
  </table>

</body>
</html>
