<!DOCTYPE html>
<html>
<img width="250" height="250" alt="parti_logo" src="https://github.com/user-attachments/assets/cdb1da0f-598d-4f94-af35-69551625e191" />
<body style="font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; line-height: 1.6; color: #333; max-width: 1000px; margin: auto; padding: 40px; background-color: #f4f7f6;">
  <div style="background-color: #ffffff; padding: 40px; border-radius: 8px; box-shadow: 0 4px 15px rgba(0,0,0,0.05);">
    <h1 style="color: #2c3e50; border-bottom: 3px solid #3498db; padding-bottom: 15px; margin-top: 0;">Parti API Documentation</h1>
    <p style="font-size: 1.1em; color: #555;">
      Technical reference for the <strong>Parti.com</strong> v2 Profile and Livestreaming API. 
    </p>
    <div style="background-color: #e8f4fd; border-left: 5px solid #3498db; padding: 15px; margin: 20px 0;">
      <strong>Authentication:</strong> All endpoints require a <code>Bearer</code> token. 
      <br><code style="background: #fff; padding: 2px 5px; border-radius: 3px;">Authorization: Bearer [REDACTED]</code>
    </div>
    <h2 style="color: #2c3e50; margin-top: 40px;">API Endpoints</h2>
    <div style="margin-bottom: 30px;">
      <h3 style="color: #2980b9;">1. Global Livestream Feed</h3>
      <p>List all active streams.</p>
      <pre style="background: #2d3436; color: #fab1a0; padding: 15px; border-radius: 5px; overflow-x: auto;">GET /parti_v2/profile/get_livestream_channel_info/live?limit=30&offset=0</pre>
    </div>
    <div style="margin-bottom: 30px;">
      <h3 style="color: #2980b9;">2. User Profile Information</h3>
      <p>Fetch account metadata, social handles, and description.</p>
      <pre style="background: #2d3436; color: #fab1a0; padding: 15px; border-radius: 5px; overflow-x: auto;">GET /parti_v2/profile/user_profile/{user_id}</pre>
    </div>
    <div style="margin-bottom: 30px; border: 1px solid #3498db; padding: 20px; border-radius: 8px;">
      <h3 style="color: #2980b9; margin-top: 0;">3. User Profile Feed & Archive</h3>
      <p>Retrieve a user's post history and <strong>archived livestream recordings (VODs)</strong>.</p>
      <pre style="background: #2d3436; color: #fab1a0; padding: 15px; border-radius: 5px; overflow-x: auto;">GET /parti_v2/profile/user_profile_feed/{user_id}?limit=5</pre>
      <div style="background: #f9f9f9; border-left: 4px solid #2ecc71; padding: 10px; margin-top: 10px;">
        <strong>Key Field for Archiving:</strong><br>
        <code>livestream_recording</code>: Use this URL to download/mirror past broadcasts.
      </div>
      <p><strong>Example Response Object:</strong></p>
      <pre style="background: #272822; color: #a6e22e; padding: 10px; font-size: 0.85em; border-radius: 5px;">
{
  "feed_id": 137948,
  "post_content": "Transmisión de los mejores videos...",
  "livestream_recording": "https://media.parti.com/.../archive/main.m3u8",
  "likes_count": 0,
  "created_at": 1773982988
}</pre>
    </div>
    <div style="margin-bottom: 30px;">
      <h3 style="color: #2980b9;">4. Channel Moderators</h3>
      <pre style="background: #2d3436; color: #fab1a0; padding: 15px; border-radius: 5px; overflow-x: auto;">GET /parti_v2/profile/livestream/moderators/{user_id}</pre>
    </div>
    <h2 style="color: #2c3e50; margin-top: 40px; border-top: 1px solid #eee; padding-top: 20px;">Schema Reference</h2>
    <table style="width: 100%; border-collapse: collapse; background: #fff;">
      <tr style="background-color: #34495e; color: #fff; text-align: left;">
        <th style="padding: 12px; border: 1px solid #ddd;">Field</th>
        <th style="padding: 12px; border: 1px solid #ddd;">Description</th>
      </tr>
      <tr>
        <td style="padding: 10px; border: 1px solid #ddd;"><code>livestream_recording</code></td>
        <td style="padding: 10px; border: 1px solid #ddd;">HLS playlist URL for the archived stream session.</td>
      </tr>
      <tr>
        <td style="padding: 10px; border: 1px solid #ddd;"><code>event_file</code></td>
        <td style="padding: 10px; border: 1px solid #ddd;">Thumbnail image captured during the live event.</td>
      </tr>
      <tr>
        <td style="padding: 10px; border: 1px solid #ddd;"><code>created_at</code></td>
        <td style="padding: 10px; border: 1px solid #ddd;">Unix timestamp of the post/recording.</td>
      </tr>
    </table>
    <footer style="margin-top: 50px; font-size: 0.8em; color: #95a5a6; text-align: center;">
      Parti API Documentation v2.0 &bull; 2026
    </footer>

  </div>

</body>
</html>
