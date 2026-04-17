ELITE DEALS HUB V2 (IMPROVED)

WHAT YOU HAVE:
- Landing page (sales optimized)
- Dashboard page
- Admin panel
- Mock STK backend

HOW TO RUN:

FRONTEND:
index.html 

BACKEND:
cd backend
npm init -y
npm install express
node server.js

NEXT STEP (IMPORTANT):
To make real money system:
- Add Firebase (users + login)
- Add real M-Pesa Daraja APIasync function pay(amount) {
  const phoneInput = document.getElementById("phone").value;

  if (!phoneInput) {
    alert("Enter phone number");
    return;
  }

  // Convert to 254 format
  let phone = phoneInput;
  if (phone.startsWith("0")) {
    phone = "254" + phone.substring(1);
  }

  try {
    const res = await fetch("https://YOUR-BACKEND-URL/stkpush", {
      method: "POST",
      headers: {
        "Content-Type": "application/json",
      },
      body: JSON.stringify({ phone, amount }),
    });

    const data = await res.json();
    alert("Check your phone for M-Pesa prompt");
  } catch (err) {
    alert("Error connecting to payment server");
  }
}
- Deploy on Vercel + Render
