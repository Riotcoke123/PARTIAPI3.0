<!DOCTYPE html>
<html>


  <h1 style="color: #2c3e50; border-bottom: 2px solid #eee; padding-bottom: 10px;">Parti Live Stream API Documentation</h1>

  <p>
    Comprehensive guide for interacting with the <strong>Parti.com</strong> livestream and moderation management system.
  </p>

  <hr style="border: 0; height: 1px; background: #eee; margin: 20px 0;" />

  <h2 style="color: #2980b9;">1. Authentication</h2>
  <p>All requests must include the following header:</p>
  <div style="background-color: #f8f9fa; padding: 15px; border-left: 5px solid #2980b9; font-family: monospace; border-radius: 4px;">
    <strong>Authorization:</strong> Bearer ...............................
  </div>

  <hr style="border: 0; height: 1px; background: #eee; margin: 20px 0;" />

  <h2 style="color: #2980b9;">2. Livestream Endpoints</h2>

  <h3 style="background: #f1f1f1; padding: 8px; border-radius: 4px;">GET /live</h3>
  <p>Fetch active livestream channel information with pagination support.</p>
  <pre style="background: #fdf6e3; padding: 10px; border: 1px solid #ddd;">GET https://prod-api.parti.com/parti_v2/profile/get_livestream_channel_info/live?limit=30&offset=0</pre>

  <h3 style="background: #f1f1f1; padding: 8px; border-radius: 4px;">GET /moderators/{id}</h3>
  <p>Retrieve the list of moderators assigned to a specific streamer's channel.</p>
  <pre style="background: #fdf6e3; padding: 10px; border: 1px solid #ddd;">GET https://prod-api.parti.com/parti_v2/profile/livestream/moderators/{id}</pre>
  
  <p><strong>Example:</strong> Fetching moderators for <code>miltserr</code> (ID: 667897):</p>
  <code style="display: block; background: #eee; padding: 5px; margin-bottom: 10px;">https://prod-api.parti.com/parti_v2/profile/livestream/moderators/667897</code>

  <hr style="border: 0; height: 1px; background: #eee; margin: 20px 0;" />

  <h2 style="color: #2980b9;">3. Endpoint Specifications</h2>

  <table style="width: 100%; border-collapse: collapse; margin-top: 10px;">
    <thead>
      <tr style="background-color: #2980b9; color: white;">
        <th style="padding: 12px; text-align: left; border: 1px solid #ddd;">Parameter</th>
        <th style="padding: 12px; text-align: left; border: 1px solid #ddd;">Type</th>
        <th style="padding: 12px; text-align: left; border: 1px solid #ddd;">Description</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td style="padding: 10px; border: 1px solid #ddd;"><code>id</code></td>
        <td style="padding: 10px; border: 1px solid #ddd;">Path</td>
        <td style="padding: 10px; border: 1px solid #ddd;">The <code>user_id</code> of the streamer.</td>
      </tr>
      <tr>
        <td style="padding: 10px; border: 1px solid #ddd;"><code>limit</code></td>
        <td style="padding: 10px; border: 1px solid #ddd;">Query</td>
        <td style="padding: 10px; border: 1px solid #ddd;">Number of records to return (Default: 30).</td>
      </tr>
      <tr>
        <td style="padding: 10px; border: 1px solid #ddd;"><code>offset</code></td>
        <td style="padding: 10px; border: 1px solid #ddd;">Query</td>
        <td style="padding: 10px; border: 1px solid #ddd;">Pagination offset.</td>
      </tr>
    </tbody>
  </table>

  <hr style="border: 0; height: 1px; background: #eee; margin: 20px 0;" />

  <h2 style="color: #2980b9;">4. Response Structure</h2>
  <div style="background: #272822; color: #f8f8f2; padding: 15px; border-radius: 5px; font-family: 'Courier New', Courier, monospace;">
    <pre>
// GET /moderators/667897
[] // Returns empty array if no moderators are assigned
    </pre>
  </div>

</body>
</html>
