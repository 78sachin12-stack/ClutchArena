Clutch Arena (powered by Beast Games) - go live in 4 steps

1. Upload index.html and admin.html to Netlify (drag and drop the whole folder) or Vercel.
   Open the site from the hosted link, not inside a chat app preview, or Supabase will not connect.
2. Supabase project "Clutch Arena": Authentication > Providers > Email > "Confirm email" must be OFF.
3. Supabase > SQL Editor: run these two files ONCE, in this order:
     database/admin_leaderboard.sql   (lets the admin panel save the leaderboard)
     database/my_opponent.sql         (shows each paid player their opponent's UID in My bookings)
   If either one errors, the table or column names differ. Send the table structure and fix the SQL.
   Do NOT re-run the older base setup SQL on the live project.
4. Open the live link. The badge on the home page should say "Live". Register a test account,
   book a slot, scan the UPI QR (beastgames@ibl) and send a test receipt.

Admin: open admin.html (or log in as admin on the site). Menu (3 lines, top right):
  Overview, Payments, Rooms, Daily, Bracket, Leaderboard.
  Payments: mark Paid and UID ok. Receipts are in Storage "receipts", profile shots in "profiles".
  Leaderboard: add match results per team, then press Save.

Custom rooms: players make their own room. When two paid players share a slot pair
(slots 1+2, 3+4, ...), each sees the other's UID in My bookings, creates a custom room,
plays, and emails the result. Pairs are by slot number.
