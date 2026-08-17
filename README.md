

<<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>ANGEL GIFT CARD</title>

<style>
*{box-sizing:border-box}

body{
    margin:0;
    font-family:Arial,sans-serif;
    background:linear-gradient(135deg,#080b20,#17104a,#071d35);
    color:white;
    min-height:100vh;
}

.app{
    max-width:480px;
    margin:auto;
    min-height:100vh;
    background:rgba(7,12,35,.75);
}

header{
    padding:22px 20px;
    display:flex;
    justify-content:space-between;
    align-items:center;
    border-bottom:1px solid #ffffff18;
}

.logo{
    font-weight:900;
    font-size:21px;
}

.logo span{
    color:#ffd34e;
}

main{
    padding:20px;
}

.card{
    background:linear-gradient(135deg,#705cff,#a443ff);
    border-radius:24px;
    padding:22px;
    box-shadow:0 15px 35px #0005;
    margin-bottom:18px;
}

.balance{
    font-size:38px;
    font-weight:900;
    margin:8px 0;
}

.muted{
    color:#c9c8dc;
    font-size:13px;
}

.grid{
    display:grid;
    grid-template-columns:1fr 1fr;
    gap:12px;
}

.action{
    border:1px solid #ffffff18;
    background:#ffffff0c;
    color:white;
    border-radius:18px;
    padding:18px 10px;
    text-align:center;
    cursor:pointer;
}

.action:hover{
    background:#ffffff16;
    transform:translateY(-2px);
}

.icon{
    font-size:25px;
    display:block;
    margin-bottom:7px;
}

.section{
    display:none;
}

.section.active{
    display:block;
}

.panel{
    background:#ffffff0b;
    border:1px solid #ffffff12;
    border-radius:20px;
    padding:18px;
}

input,select{
    width:100%;
    padding:14px;
    margin:8px 0;
    border-radius:12px;
    border:1px solid #ffffff18;
    background:#0c1230;
    color:white;
    outline:none;
}

.primary{
    width:100%;
    border:0;
    border-radius:13px;
    padding:14px;
    background:#ffd34e;
    color:#17120a;
    font-weight:800;
    cursor:pointer;
    margin-top:8px;
}

.back{
    background:none;
    border:0;
    color:#ffd34e;
    padding:0 0 15px;
    cursor:pointer;
}

nav{
    position:sticky;
    bottom:0;
    background:#090d25ee;
    border-top:1px solid #ffffff14;
    display:grid;
    grid-template-columns:repeat(4,1fr);
    padding:10px;
}

nav button{
    background:none;
    border:0;
    color:#bfc0d5;
    padding:8px;
    font-size:12px;
    cursor:pointer;
}

nav button.active{
    color:#ffd34e;
}

.badge{
    background:#ffffff18;
    padding:7px 10px;
    border-radius:20px;
    font-size:12px;
}

.notice{
    font-size:12px;
    line-height:1.5;
    color:#c8c8d8;
    margin-top:12px;
}

#signup{
    position:fixed;
    inset:0;
    background:linear-gradient(135deg,#090b22,#30105d);
    z-index:5;
    display:flex;
    align-items:center;
    justify-content:center;
    padding:20px;
}

.signupbox{
    width:100%;
    max-width:430px;
    background:#ffffff0b;
    border:1px solid #ffffff16;
    border-radius:26px;
    padding:25px;
}

.small{
    font-size:12px;
    color:#aaaec8;
}
</style>
</head>

<body>

<!-- SIGN UP -->

<div id="signup">

    <div class="signupbox">

        <div class="logo">
            ✨ ANGEL <span>GIFT CARD</span>
        </div>

        <h1>Create your account</h1>

        <p class="muted">
            Welcome to Angel Gift Card.
        </p>

        <input
            id="name"
            placeholder="Full name"
        >

        <input
            id="email"
            type="email"
            placeholder="Email address"
        >

        <input
            id="phone"
            placeholder="Phone number"
        >

        <input
            id="password"
            type="password"
            placeholder="Password"
        >

        <button
            class="primary"
            onclick="createAccount()"
        >
            Sign Up
        </button>

        <p class="small">
            Create your Angel Gift Card account to access your wallet.
        </p>

    </div>

</div>


<!-- MAIN APP -->

<div
    class="app"
    id="app"
    style="display:none"
>

<header>

    <div class="logo">
        ✨ ANGEL <span>GIFT CARD</span>
    </div>

    <span
        class="badge"
        id="userBadge"
    >
        Member
    </span>

</header>


<main>

<!-- HOME -->

<section
    id="home"
    class="section active"
>

    <div class="card">

        <div class="muted">
            Available Balance
        </div>

        <div class="balance">
            ₦<span id="balance">0</span>
        </div>

        <div class="muted">
            Angel Gift Card Wallet
        </div>

    </div>


    <div class="grid">

        <button
            class="action"
            onclick="show('redeem')"
        >
            <span class="icon">🎁</span>
            Redeem Card
        </button>


        <button
            class="action"
            onclick="show('withdraw')"
        >
            <span class="icon">💸</span>
            Withdraw
        </button>


        <button
            class="action"
            onclick="show('trade')"
        >
            <span class="icon">🔄</span>
            Trade
        </button>


        <button
            class="action"
            onclick="show('deposit')"
        >
            <span class="icon">➕</span>
            Deposit
        </button>

    </div>

</section>


<!-- REDEEM -->

<section
    id="redeem"
    class="section"
>

<button
    class="back"
    onclick="show('home')"
>
    ← Back
</button>

<div class="panel">

    <h2>
        Redeem Gift Card
    </h2>

    <input
        id="giftcode"
        placeholder="Enter gift card code"
    >

    <button
        class="primary"
        onclick="redeemCard()"
    >
        Redeem Card
    </button>

</div>

</section>


<!-- WITHDRAW -->

<section
    id="withdraw"
    class="section"
>

<button
    class="back"
    onclick="show('home')"
>
    ← Back
</button>

<div class="panel">

    <h2>
        Withdraw
    </h2>

    <input
        id="withdrawAmount"
        type="number"
        placeholder="Amount (₦)"
    >

    <input
        placeholder="Recipient account number"
    >

    <input
        placeholder="Recipient bank"
    >

    <button
        class="primary"
        onclick="withdrawMoney()"
    >
        Request Withdrawal
    </button>

</div>

</section>


<!-- DEPOSIT -->

<section
    id="deposit"
    class="section"
>

<button
    class="back"
    onclick="show('home')"
>
    ← Back
</button>

<div class="panel">

    <h2>
        Deposit
    </h2>

    <p class="muted">
        Deposit Account Details
    </p>


    <div
        style="
        background:#ffffff0c;
        border:1px solid #ffffff18;
        border-radius:16px;
        padding:15px;
        margin-top:12px;
        "
    >

        <p>
            <span class="muted">
                Bank
            </span>
            <br>

            <b>
                FairMoney Microfinance Bank LTD
            </b>
        </p>


        <p>
            <span class="muted">
                Account Number
            </span>
            <br>

            <b
                style="font-size:22px"
            >
                2026457764
            </b>
        </  document.getElementById('userBadge').textContent=name.split(' ')[0];
  document.getElementById('balance').textContent='13,000';
  alert("You're welcome to Angel Gift Card! Your starting wallet balance is ₦13,000.");
}
function show(id,btn){
  document.querySelectorAll('.section').forEach(s=>s.classList.remove('active'));
  document.getElementById(id).classList.add('active');
  document.querySelectorAll('nav button').forEach(b=>b.classList.remove('active'));
  if(btn)btn.classList.add('active');
  window.scrollTo(0,0);
}
</script>
</body>
</html>
