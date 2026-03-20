<!DOCTYPE html>
<html>
<img width="250" height="250" alt="parti_logo" src="https://github.com/user-attachments/assets/cdb1da0f-598d-4f94-af35-69551625e191" />

<body style="font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; line-height: 1.6; color: #333; max-width: 1000px; margin: auto; padding: 40px; background-color: #f4f7f6;">

  <div style="background-color: #ffffff; padding: 40px; border-radius: 8px; box-shadow: 0 4px 15px rgba(0,0,0,0.05);"> 
    <h1 style="color: #2c3e50; border-bottom: 3px solid #3498db; padding-bottom: 15px; margin-top: 0;">Parti API Documentation</h1>
    <p style="font-size: 1.1em; color: #555;">
      Technical reference for <strong>Parti.com</strong> v2 Profile and Livestreaming API.
    </p>
    <div style="background-color: #2d3436; border-left: 5px solid #e17055; padding: 15px; margin: 20px 0; color: #dfe6e9;">
      <strong>Authentication:</strong> Bearer token required in the header.
      <br><code style="color: #fab1a0;">Authorization: Bearer [REDACTED]</code>
    </div>
    <h2 style="color: #2c3e50; margin-top: 40px;">API Endpoints</h2>
    <div style="margin-bottom: 30px; border: 1px solid #ddd; padding: 20px; border-radius: 8px;">
      <h3 style="color: #d63031; margin-top: 0;">1. Global Livestream Feed (Bulk Discovery)</h3>
      <p>Returns a broad list of active streams. Use <code>limit=100</code> for high-volume monitoring.</p>
      <pre style="background: #2d3436; color: #fab1a0; padding: 15px; border-radius: 5px; overflow-x: auto;">GET /parti_v2/profile/get_livestream_channel_info/live?limit=100&offset=0</pre>
      <p><strong>Response Schema Highlights:</strong></p>
      <ul style="font-size: 0.9em; color: #636e72;">
        <li><strong>playback_url:</strong> Current DVR-enabled stream.</li>
        <li><strong>original_playback_url:</strong> The direct live HLS manifest.</li>
        <li><strong>event_file:</strong> Live thumbnail/screenshot URL.</li>
      </ul>
    </div>
    <div style="margin-bottom: 30px;">
      <h3 style="color: #2980b9;">2. User Profile Feed & Archive</h3>
      <p>Retrieve a user's post history and <strong>archived livestream recordings (VODs)</strong>.</p>
      <pre style="background: #2d3436; color: #fab1a0; padding: 15px; border-radius: 5px; overflow-x: auto;">GET /parti_v2/profile/user_profile_feed/{user_id}?limit=5</pre>
    </div>
    <div style="margin-bottom: 30px;">
      <h3 style="color: #2980b9;">3. User Profile Metadata</h3>
      <pre style="background: #2d3436; color: #fab1a0; padding: 15px; border-radius: 5px; overflow-x: auto;">GET /parti_v2/profile/user_profile/{user_id}</pre>
    </div>
    <div style="margin-bottom: 30px;">
      <h3 style="color: #2980b9;">4. Specific Channel Info</h3>
      <pre style="background: #2d3436; color: #fab1a0; padding: 15px; border-radius: 5px; overflow-x: auto;">GET /parti_v2/profile/get_livestream_channel_info/{user_id}</pre>
    </div>
    <h2 style="color: #2c3e50; margin-top: 40px; border-top: 1px solid #eee; padding-top: 20px;">Stream Parameter Reference</h2>
    <table style="width: 100%; border-collapse: collapse; background: #fff; font-size: 0.9em;">
      <tr style="background-color: #34495e; color: #fff; text-align: left;">
        <th style="padding: 12px; border: 1px solid #ddd;">Parameter</th>
        <th style="padding: 12px; border: 1px solid #ddd;">Description</th>
      </tr>
      <tr>
        <td style="padding: 10px; border: 1px solid #ddd;"><code>channel_arn</code></td>
        <td style="padding: 10px; border: 1px solid #ddd;">Unique AWS/GCP resource identifier for the stream channel.</td>
      </tr>
      <tr>
        <td style="padding: 10px; border: 1px solid #ddd;"><code>dvr_url</code></td>
        <td style="padding: 10px; border: 1px solid #ddd;">Playlist allowing viewers to seek back in the live stream.</td>
      </tr>
      <tr>
        <td style="padding: 10px; border: 1px solid #ddd;"><code>viewers_count</code></td>
        <td style="padding: 10px; border: 1px solid #ddd;">Real-time concurrent viewer metrics.</td>
      </tr>
    </table>
    <footer style="margin-top: 50px; font-size: 0.8em; color: #95a5a6; text-align: center;">
      Parti API Documentation v2.1 &bull; 2026
    </footer>

  </div>

</body>
</html>
