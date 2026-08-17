
code" placeholder="Enter gift card code">
<button class="primary" onclick="alert('Gift card redemption is not connected to a live card service.')">Redeem Card</button>
</div></section>

<section id="withdraw" class="section">
<button class="back" onclick="show('home')">← Back</button>
<div class="panel"><h2>Withdraw</h2>
<input type="number" placeholder="Amount (₦)">
<input placeholder="Recipient account number">
<input placeholder="Recipient bank">
<button class="primary" onclick="alert('Withdrawal request received.')">Request Withdrawal</button>
</div></section>

<section id="deposit" class="section">
<button class="back" onclick="show('home')">← Back</button>
<div class="panel"><h2>Deposit</h2>
<p class="muted">Deposit Account Details</p>
<div style="background:#ffffff0c;border:1px solid #ffffff18;border-radius:16px;padding:15px;margin-top:12px">
  <p><span class="muted">Bank</span><br><b>FairMoney Microfinance Bank LTD</b></p>
  <p><span class="muted">Account Number</span><br><b style="font-size:22px">2026457764</b></p>
  <p><span class="muted">Account Name</span><br><b>Sheriff Ismail</b></p>
</div>
<p class="notice">Please confirm the account name and number carefully before making any transaction.</p>
</div></section>

<section id="trade" class="section">
<button class="back" onclick="show('home')">← Back</button>
<div class="panel"><h2>Trade</h2>
<select><option>Gift Card → NGN</option><option>NGN → Gift Card</option><option>USD → NGN</option><option>EUR → NGN</option></select>
<input type="number" placeholder="Amount">
<button class="primary" onclick="alert('Trading is not connected to a live exchange.')">Continue</button>
</div></section>

<section id="currency" class="section">
<button class="back" onclick="show('home')">← Back</button>
<div class="panel"><h2>Change Currency</h2>
<select id="currencySelect" onchange="document.getElementById('currencyLabel').textContent=this.value">
<option>NGN — Nigerian Naira</option><option>USD — US Dollar</option><option>GBP — British Pound</option><option>EUR — Euro</option><option>GHS — Ghanaian Cedi</option>
</select>
<p class="muted">Selected: <span id="currencyLabel">NGN — Nigerian Naira</span></p>
</div></section>
</main>

<nav>
<button class="active" onclick="show('home',this)">⌂<br>Home</button>
<button onclick="show('currency',this)">◎<br>Currency</button>
<button onclick="show('redeem',this)">🎁<br>Redeem</button>
<button onclick="show('withdraw',this)">↗<br>Withdraw</button>
</nav>
</div>

<script>
function createAccount(){
  const name=document.getElementById('name').value.trim();
  const email=document.getElementById('email').value.trim();
  const phone=document.getElementById('phone').value.trim();
  const password=document.getElementById('password').value;
  if(!name||!email||!phone||!password){alert('Please complete all fields.');return}
  document.getElementById('signup').style.display='none';
  document.getElementById('app').style.display='block';
  document.getElementById('userBadge').textContent=name.split(' ')[0];
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
