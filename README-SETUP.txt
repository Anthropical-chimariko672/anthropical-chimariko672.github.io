TANSI SECURE PODCAST PORTFOLIO V6

WHAT THIS VERSION DOES
- Public index.html has NO Edit button.
- admin.html is a separate private editor.
- Email/password login is handled by Supabase Auth.
- RLS in Supabase is what actually protects editing rights.
- You edit from your iPhone, then tap Publish.

SETUP FROM IPHONE
1. Create a Supabase project at supabase.com.
2. In Authentication > Users, create ONE user using your own email/password.
3. Open SQL Editor and paste supabase-schema.sql. Replace YOUR_AUTH_USER_UUID with the UUID of your user before running it.
4. Open Project Settings > API. Copy the Project URL and the anon/publishable key.
5. Open config.js in GitHub and replace the two PASTE_YOUR... values. Never put a service_role/secret key in config.js.
6. Upload index.html, admin.html and config.js to the root of your GitHub Pages repository. Keep supabase-schema.sql private or delete it from the public repo after setup.
7. Open your public site: https://zalabakatansi-hue.github.io/
8. Open the editor directly: https://zalabakatansi-hue.github.io/admin.html
9. Sign in with the Supabase user you created.
10. Make edits and tap Publish. The public site reads the published row from Supabase.

IMPORTANT
- The Supabase anon/publishable key is okay in browser code when RLS is configured.
- NEVER expose a service_role key.
- If you want to change the login password, do it in Supabase Authentication > Users.
- The admin URL can be visited by anyone, but only the authorized Auth user can load or publish portfolio data.
