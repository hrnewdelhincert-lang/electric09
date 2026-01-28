<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Electric Market - Complete System</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
      min-height: 100vh;
      padding: 20px;
    }

    .container {
      max-width: 1400px;
      margin: 0 auto;
    }

    .header {
      background: white;
      padding: 20px;
      border-radius: 15px;
      box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
      margin-bottom: 20px;
    }

    .header h1 {
      font-size: 28px;
      color: #333;
      display: flex;
      align-items: center;
      gap: 10px;
    }

    .card {
      background: white;
      padding: 30px;
      border-radius: 15px;
      box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
      margin-bottom: 20px;
    }

    .form-group {
      margin-bottom: 20px;
    }

    label {
      display: block;
      margin-bottom: 8px;
      color: #555;
      font-weight: 500;
    }

    input, select, textarea {
      width: 100%;
      padding: 12px 15px;
      border: 2px solid #e1e8ed;
      border-radius: 8px;
      font-size: 16px;
      transition: all 0.3s;
    }

    input:focus, select:focus, textarea:focus {
      outline: none;
      border-color: #667eea;
    }

    .btn {
      padding: 12px 24px;
      border: none;
      border-radius: 8px;
      font-size: 16px;
      font-weight: 600;
      cursor: pointer;
      transition: all 0.3s;
    }

    .btn-full {
      width: 100%;
    }

    .btn-primary {
      background: #667eea;
      color: white;
    }

    .btn-primary:hover {
      background: #5568d3;
      transform: translateY(-2px);
    }

    .btn-success {
      background: #10b981;
      color: white;
    }

    .btn-success:hover {
      background: #059669;
    }

    .btn-danger {
      background: #ef4444;
      color: white;
    }

    .btn-danger:hover {
      background: #dc2626;
    }

    .btn-secondary {
      background: #6b7280;
      color: white;
    }

    .btn-group {
      display: flex;
      gap: 10px;
      flex-wrap: wrap;
    }

    .btn-group .btn {
      flex: 1;
      min-width: 120px;
    }

    .balance-display {
      background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
      color: white;
      padding: 25px;
      border-radius: 12px;
      text-align: center;
      margin-bottom: 20px;
    }

    .balance-display h2 {
      font-size: 18px;
      margin-bottom: 10px;
      opacity: 0.9;
    }

    .balance-display .amount {
      font-size: 42px;
      font-weight: bold;
    }

    .hidden {
      display: none !important;
    }

    .alert {
      padding: 12px 15px;
      border-radius: 8px;
      margin-bottom: 20px;
      font-weight: 500;
    }

    .alert-success {
      background: #d1fae5;
      color: #065f46;
      border: 1px solid #10b981;
    }

    .alert-error {
      background: #fee2e2;
      color: #991b1b;
      border: 1px solid #ef4444;
    }

    .link-btn {
      display: inline-block;
      color: #667eea;
      text-decoration: none;
      margin-top: 15px;
      font-weight: 500;
      cursor: pointer;
    }

    .link-btn:hover {
      text-decoration: underline;
    }

    /* Products Grid */
    .products-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
      gap: 20px;
      margin-top: 20px;
    }

    .product-card {
      background: white;
      border-radius: 12px;
      padding: 20px;
      text-align: center;
      box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
      transition: all 0.3s;
    }

    .product-card:hover {
      transform: translateY(-5px);
      box-shadow: 0 8px 15px rgba(0, 0, 0, 0.2);
    }

    .product-image {
      width: 100%;
      height: 150px;
      background: #f3f4f6;
      border-radius: 8px;
      margin-bottom: 15px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 48px;
    }

    .product-name {
      font-size: 18px;
      font-weight: 600;
      color: #1f2937;
      margin-bottom: 10px;
    }

    .product-price {
      font-size: 24px;
      font-weight: bold;
      color: #667eea;
      margin-bottom: 15px;
    }

    .product-card .btn {
      width: 100%;
      padding: 10px;
    }

    /* Tables */
    .data-table {
      width: 100%;
      border-collapse: collapse;
      margin-top: 20px;
    }

    .data-table th {
      background: #f9fafb;
      padding: 12px;
      text-align: left;
      font-weight: 600;
      border-bottom: 2px solid #e5e7eb;
    }

    .data-table td {
      padding: 12px;
      border-bottom: 1px solid #e5e7eb;
    }

    .data-table tr:hover {
      background: #f9fafb;
    }

    .badge {
      display: inline-block;
      padding: 4px 12px;
      border-radius: 12px;
      font-size: 12px;
      font-weight: 600;
    }

    .badge-success {
      background: #d1fae5;
      color: #065f46;
    }

    .badge-warning {
      background: #fef3c7;
      color: #92400e;
    }

    .badge-info {
      background: #dbeafe;
      color: #1e40af;
    }

    .stats-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
      gap: 20px;
      margin-bottom: 20px;
    }

    .stat-card {
      background: white;
      padding: 20px;
      border-radius: 12px;
      box-shadow: 0 4px 6px rgba(0, 0, 0, 0.07);
      border-left: 4px solid #667eea;
    }

    .stat-card h3 {
      font-size: 14px;
      color: #6b7280;
      margin-bottom: 10px;
    }

    .stat-card .value {
      font-size: 28px;
      font-weight: bold;
      color: #1f2937;
    }

    .nav-tabs {
      display: flex;
      gap: 10px;
      margin-bottom: 20px;
      border-bottom: 2px solid #e5e7eb;
      padding-bottom: 10px;
    }

    .nav-tab {
      padding: 10px 20px;
      background: none;
      border: none;
      font-size: 16px;
      font-weight: 600;
      color: #6b7280;
      cursor: pointer;
      border-bottom: 3px solid transparent;
      transition: all 0.3s;
    }

    .nav-tab.active {
      color: #667eea;
      border-bottom-color: #667eea;
    }

    .nav-tab:hover {
      color: #667eea;
    }

    .transaction-item {
      display: flex;
      justify-content: space-between;
      padding: 12px;
      border-bottom: 1px solid #e5e7eb;
    }

    .transaction-type {
      font-weight: 600;
      text-transform: capitalize;
    }

    .transaction-date {
      font-size: 12px;
      color: #6b7280;
    }

    .transaction-amount {
      font-weight: bold;
    }

    .transaction-amount.positive {
      color: #10b981;
    }

    .transaction-amount.negative {
      color: #ef4444;
    }

    @media (max-width: 768px) {
      .products-grid {
        grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
      }

      .stats-grid {
        grid-template-columns: 1fr;
      }

      .btn-group {
        flex-direction: column;
      }

      .data-table {
        font-size: 14px;
      }
    }
  </style>
</head>
<body>
  <div class="container">
    <!-- Login/Register Page -->
    <div id="authPage">
      <div class="header">
        <h1>⚡ Electric Market</h1>
      </div>

      <div class="card">
        <!-- Login Form -->
        <div id="loginForm">
          <h2 style="margin-bottom: 20px; color: #333;">Login</h2>
          <div id="loginAlert"></div>
          <form onsubmit="handleLogin(event)">
            <div class="form-group">
              <label>Mobile Number</label>
              <input type="text" id="loginMobile" maxlength="10" placeholder="Enter 10-digit mobile number" required>
            </div>
            <div class="form-group">
              <label>Password</label>
              <input type="password" id="loginPassword" placeholder="Enter your password" required>
            </div>
            <button type="submit" class="btn btn-primary btn-full">Login</button>
          </form>
          <a class="link-btn" onclick="showRegister()">Don't have an account? Register</a>
        </div>

        <!-- Register Form -->
        <div id="registerForm" class="hidden">
          <h2 style="margin-bottom: 20px; color: #333;">Register</h2>
          <div id="registerAlert"></div>
          <form onsubmit="handleRegister(event)">
            <div class="form-group">
              <label>Mobile Number</label>
              <input type="text" id="registerMobile" maxlength="10" placeholder="Enter 10-digit mobile number" required>
            </div>
            <div class="form-group">
              <label>Password</label>
              <input type="password" id="registerPassword" placeholder="At least 6 characters" required>
            </div>
            <div class="form-group">
              <label>Confirm Password</label>
              <input type="password" id="registerConfirmPassword" placeholder="Re-enter password" required>
            </div>
            <button type="submit" class="btn btn-primary btn-full">Register</button>
          </form>
          <a class="link-btn" onclick="showLogin()">Already have an account? Login</a>
        </div>
      </div>
    </div>

    <!-- User Dashboard -->
    <div id="userDashboard" class="hidden">
      <div class="header">
        <h1>⚡ Electric Market</h1>
        <p style="margin-top: 10px;">Welcome: <strong id="userMobile"></strong></p>
      </div>

      <div class="card">
        <div class="balance-display">
          <h2>Balance</h2>
          <div class="amount">$<span id="userBalance">0</span></div>
        </div>

        <div class="btn-group">
          <button class="btn btn-primary" onclick="showRechargeForm()">Recharge</button>
          <button class="btn btn-danger" onclick="showWithdrawForm()">Withdraw</button>
          <button class="btn btn-secondary" onclick="logout()">Logout</button>
        </div>
      </div>

      <!-- Navigation Tabs -->
      <div class="card">
        <div class="nav-tabs">
          <button class="nav-tab active" onclick="showUserTab('products')">🛒 Products</button>
          <button class="nav-tab" onclick="showUserTab('orders')">📦 My Orders</button>
          <button class="nav-tab" onclick="showUserTab('transactions')">💰 Transactions</button>
        </div>

        <!-- Products Tab -->
        <div id="productsTab">
          <h3 style="margin-bottom: 20px;">Available Products</h3>
          <div id="productsGrid" class="products-grid"></div>
        </div>

        <!-- Orders Tab -->
        <div id="ordersTab" class="hidden">
          <h3 style="margin-bottom: 20px;">My Orders</h3>
          <div id="userOrders">
            <p style="text-align: center; color: #6b7280;">No orders yet</p>
          </div>
        </div>

        <!-- Transactions Tab -->
        <div id="transactionsTab" class="hidden">
          <h3 style="margin-bottom: 20px;">Transaction History</h3>
          <div id="userTransactions">
            <p style="text-align: center; color: #6b7280;">No transactions yet</p>
          </div>
        </div>
      </div>

      <!-- Recharge Form -->
      <div id="rechargeForm" class="card hidden">
        <h3 style="margin-bottom: 20px;">Recharge Account</h3>
        <div id="rechargeAlert"></div>
        <div class="form-group">
          <label>Amount ($)</label>
          <input type="number" id="rechargeAmount" value="100" min="1" step="0.01">
        </div>
        <div class="btn-group">
          <button class="btn btn-success" onclick="handleRecharge()">Confirm Recharge</button>
          <button class="btn btn-secondary" onclick="hideRechargeForm()">Cancel</button>
        </div>
      </div>

      <!-- Withdraw Form -->
      <div id="withdrawForm" class="card hidden">
        <h3 style="margin-bottom: 20px;">Withdraw Funds</h3>
        <div id="withdrawAlert"></div>
        <div class="form-group">
          <label>Amount ($)</label>
          <input type="number" id="withdrawAmount" min="1" step="0.01" placeholder="Enter amount">
        </div>
        <div class="btn-group">
          <button class="btn btn-danger" onclick="handleWithdraw()">Confirm Withdraw</button>
          <button class="btn btn-secondary" onclick="hideWithdrawForm()">Cancel</button>
        </div>
      </div>
    </div>

    <!-- Admin Dashboard -->
    <div id="adminDashboard" class="hidden">
      <div class="header">
        <h1>👑 Admin Control Panel</h1>
        <button class="btn btn-secondary" onclick="logout()" style="margin-top: 15px;">Logout</button>
      </div>

      <!-- Statistics -->
      <div class="stats-grid">
        <div class="stat-card">
          <h3>Total Users</h3>
          <div class="value" id="totalUsers">0</div>
        </div>
        <div class="stat-card">
          <h3>Total Balance</h3>
          <div class="value">$<span id="totalBalance">0</span></div>
        </div>
        <div class="stat-card">
          <h3>Total Orders</h3>
          <div class="value" id="totalOrders">0</div>
        </div>
        <div class="stat-card">
          <h3>Total Sales</h3>
          <div class="value">$<span id="totalSales">0</span></div>
        </div>
      </div>

      <!-- Admin Tabs -->
      <div class="card">
        <div class="nav-tabs">
          <button class="nav-tab active" onclick="showAdminTab('users')">👥 Users</button>
          <button class="nav-tab" onclick="showAdminTab('products')">📦 Products</button>
          <button class="nav-tab" onclick="showAdminTab('orders')">🛒 Orders</button>
        </div>

        <!-- Users Tab -->
        <div id="adminUsersTab">
          <h3 style="margin-bottom: 20px;">User Management</h3>
          <div style="margin-bottom: 20px;">
            <button class="btn btn-success" onclick="addDailyIncome()">Add Daily Income +$10 (ALL USERS)</button>
          </div>
          <div style="overflow-x: auto;">
            <table class="data-table">
              <thead>
                <tr>
                  <th>Mobile</th>
                  <th>Balance</th>
                  <th>Orders</th>
                  <th>Registered</th>
                  <th>Last Login</th>
                  <th>Actions</th>
                </tr>
              </thead>
              <tbody id="usersTableBody">
                <tr>
                  <td colspan="6" style="text-align: center; padding: 40px; color: #6b7280;">
                    No users registered yet
                  </td>
                </tr>
              </tbody>
            </table>
          </div>
        </div>

        <!-- Products Tab -->
        <div id="adminProductsTab" class="hidden">
          <h3 style="margin-bottom: 20px;">Product Management</h3>
          <button class="btn btn-primary" onclick="showAddProductForm()" style="margin-bottom: 20px;">+ Add New Product</button>
          
          <div id="addProductForm" class="hidden" style="margin-bottom: 20px; padding: 20px; background: #f9fafb; border-radius: 8px;">
            <h4 style="margin-bottom: 15px;">Add New Product</h4>
            <div id="productFormAlert"></div>
            <div class="form-group">
              <label>Product Name</label>
              <input type="text" id="productName" placeholder="e.g., LED Bulb">
            </div>
            <div class="form-group">
              <label>Price ($)</label>
              <input type="number" id="productPrice" min="0.01" step="0.01" placeholder="e.g., 20">
            </div>
            <div class="form-group">
              <label>Icon (Emoji)</label>
              <input type="text" id="productIcon" placeholder="e.g., 💡" maxlength="2">
            </div>
            <div class="btn-group">
              <button class="btn btn-success" onclick="addProduct()">Add Product</button>
              <button class="btn btn-secondary" onclick="hideAddProductForm()">Cancel</button>
            </div>
          </div>

          <div style="overflow-x: auto;">
            <table class="data-table">
              <thead>
                <tr>
                  <th>Icon</th>
                  <th>Product Name</th>
                  <th>Price</th>
                  <th>Orders Count</th>
                  <th>Actions</th>
                </tr>
              </thead>
              <tbody id="productsTableBody"></tbody>
            </table>
          </div>
        </div>

        <!-- Orders Tab -->
        <div id="adminOrdersTab" class="hidden">
          <h3 style="margin-bottom: 20px;">All Orders</h3>
          <div style="overflow-x: auto;">
            <table class="data-table">
              <thead>
                <tr>
                  <th>Order ID</th>
                  <th>Customer</th>
                  <th>Product</th>
                  <th>Price</th>
                  <th>Status</th>
                  <th>Date</th>
                </tr>
              </thead>
              <tbody id="ordersTableBody">
                <tr>
                  <td colspan="6" style="text-align: center; padding: 40px; color: #6b7280;">
                    No orders yet
                  </td>
                </tr>
              </tbody>
            </table>
          </div>
        </div>
      </div>
    </div>
  </div>

  <script>
    // Products Database
    const defaultProducts = [
      { id: 1, name: 'LED Bulb', price: 20, icon: '💡' },
      { id: 2, name: 'Fan', price: 80, icon: '🌀' },
      { id: 3, name: 'Iron', price: 60, icon: '🔥' },
      { id: 4, name: 'Heater', price: 120, icon: '♨️' },
      { id: 5, name: 'Extension', price: 25, icon: '🔌' },
      { id: 6, name: 'Switch', price: 15, icon: '⚡' },
      { id: 7, name: 'Socket', price: 18, icon: '🔋' },
      { id: 8, name: 'Battery', price: 35, icon: '🔋' },
      { id: 9, name: 'Inverter', price: 200, icon: '⚙️' },
      { id: 10, name: 'Solar Panel', price: 350, icon: '☀️' },
      { id: 11, name: 'Kettle', price: 45, icon: '🫖' },
      { id: 12, name: 'Mixer', price: 75, icon: '🔀' }
    ];

    // Initialize localStorage
    function initStorage() {
      if (!localStorage.getItem('users')) {
        localStorage.setItem('users', JSON.stringify([]));
      }
      if (!localStorage.getItem('transactions')) {
        localStorage.setItem('transactions', JSON.stringify([]));
      }
      if (!localStorage.getItem('products')) {
        localStorage.setItem('products', JSON.stringify(defaultProducts));
      }
      if (!localStorage.getItem('orders')) {
        localStorage.setItem('orders', JSON.stringify([]));
      }
      
      // Create admin user
      const users = getUsers();
      if (!users.find(u => u.mobile === 'ADMIN')) {
        users.push({
          mobile: 'ADMIN',
          password: 'admin123',
          balance: 0,
          role: 'admin',
          createdAt: new Date().toISOString(),
          lastLogin: null,
          totalRecharge: 0,
          totalWithdrawal: 0
        });
        saveUsers(users);
      }
    }

    // Storage helpers
    function getUsers() {
      return JSON.parse(localStorage.getItem('users') || '[]');
    }

    function saveUsers(users) {
      localStorage.setItem('users', JSON.stringify(users));
    }

    function getTransactions() {
      return JSON.parse(localStorage.getItem('transactions') || '[]');
    }

    function saveTransactions(transactions) {
      localStorage.setItem('transactions', JSON.stringify(transactions));
    }

    function getProducts() {
      return JSON.parse(localStorage.getItem('products') || '[]');
    }

    function saveProducts(products) {
      localStorage.setItem('products', JSON.stringify(products));
    }

    function getOrders() {
      return JSON.parse(localStorage.getItem('orders') || '[]');
    }

    function saveOrders(orders) {
      localStorage.setItem('orders', JSON.stringify(orders));
    }

    function getCurrentUser() {
      const mobile = localStorage.getItem('currentUser');
      if (!mobile) return null;
      return getUsers().find(u => u.mobile === mobile);
    }

    // Auth Functions
    function handleLogin(event) {
      event.preventDefault();
      const mobile = document.getElementById('loginMobile').value;
      const password = document.getElementById('loginPassword').value;

      const users = getUsers();
      const user = users.find(u => u.mobile === mobile);

      if (!user || user.password !== password) {
        showAlert('loginAlert', 'Invalid mobile number or password', 'error');
        return;
      }

      user.lastLogin = new Date().toISOString();
      saveUsers(users);
      localStorage.setItem('currentUser', mobile);

      if (user.role === 'admin') {
        showAdminDashboard();
      } else {
        showUserDashboard(user);
      }
    }

    function handleRegister(event) {
      event.preventDefault();
      const mobile = document.getElementById('registerMobile').value;
      const password = document.getElementById('registerPassword').value;
      const confirmPassword = document.getElementById('registerConfirmPassword').value;

      if (mobile.length !== 10 || !/^\d+$/.test(mobile)) {
        showAlert('registerAlert', 'Please enter a valid 10-digit mobile number', 'error');
        return;
      }

      if (password.length < 6) {
        showAlert('registerAlert', 'Password must be at least 6 characters', 'error');
        return;
      }

      if (password !== confirmPassword) {
        showAlert('registerAlert', 'Passwords do not match', 'error');
        return;
      }

      const users = getUsers();
      if (users.find(u => u.mobile === mobile)) {
        showAlert('registerAlert', 'Mobile number already registered', 'error');
        return;
      }

      users.push({
        mobile: mobile,
        password: password,
        balance: 0,
        role: 'user',
        createdAt: new Date().toISOString(),
        lastLogin: null,
        totalRecharge: 0,
        totalWithdrawal: 0
      });
      saveUsers(users);

      showAlert('registerAlert', 'Registration successful! Please login.', 'success');
      setTimeout(() => {
        showLogin();
        document.getElementById('loginMobile').value = mobile;
      }, 1500);
    }

    function logout() {
      localStorage.removeItem('currentUser');
      location.reload();
    }

    // User Dashboard Functions
    function handleRecharge() {
      const amount = parseFloat(document.getElementById('rechargeAmount').value);
      if (!amount || amount <= 0) {
        showAlert('rechargeAlert', 'Please enter a valid amount', 'error');
        return;
      }

      const users = getUsers();
      const currentMobile = localStorage.getItem('currentUser');
      const user = users.find(u => u.mobile === currentMobile);

      user.balance += amount;
      user.totalRecharge += amount;
      saveUsers(users);

      const transactions = getTransactions();
      transactions.push({
        mobile: user.mobile,
        type: 'recharge',
        amount: amount,
        balanceAfter: user.balance,
        date: new Date().toISOString()
      });
      saveTransactions(transactions);

      showAlert('rechargeAlert', 'Recharge successful!', 'success');
      setTimeout(() => {
        hideRechargeForm();
        showUserDashboard(user);
      }, 1000);
    }

    function handleWithdraw() {
      const amount = parseFloat(document.getElementById('withdrawAmount').value);
      if (!amount || amount <= 0) {
        showAlert('withdrawAlert', 'Please enter a valid amount', 'error');
        return;
      }

      const users = getUsers();
      const currentMobile = localStorage.getItem('currentUser');
      const user = users.find(u => u.mobile === currentMobile);

      if (user.balance < amount) {
        showAlert('withdrawAlert', 'Insufficient balance', 'error');
        return;
      }

      user.balance -= amount;
      user.totalWithdrawal += amount;
      saveUsers(users);

      const transactions = getTransactions();
      transactions.push({
        mobile: user.mobile,
        type: 'withdrawal',
        amount: amount,
        balanceAfter: user.balance,
        date: new Date().toISOString()
      });
      saveTransactions(transactions);

      showAlert('withdrawAlert', 'Withdrawal successful!', 'success');
      setTimeout(() => {
        hideWithdrawForm();
        showUserDashboard(user);
      }, 1000);
    }

    // Product Functions
    function buyProduct(productId) {
      const users = getUsers();
      const currentMobile = localStorage.getItem('currentUser');
      const user = users.find(u => u.mobile === currentMobile);
      const product = getProducts().find(p => p.id === productId);

      if (user.balance < product.price) {
        alert('Insufficient balance! Please recharge your account.');
        return;
      }

      if (confirm(`Buy ${product.name} for $${product.price}?`)) {
        user.balance -= product.price;
        saveUsers(users);

        // Add transaction
        const transactions = getTransactions();
        transactions.push({
          mobile: user.mobile,
          type: 'purchase',
          amount: product.price,
          product: product.name,
          balanceAfter: user.balance,
          date: new Date().toISOString()
        });
        saveTransactions(transactions);

        // Add order
        const orders = getOrders();
        orders.push({
          id: Date.now(),
          mobile: user.mobile,
          productId: product.id,
          productName: product.name,
          price: product.price,
          status: 'completed',
          date: new Date().toISOString()
        });
        saveOrders(orders);

        alert('Purchase successful!');
        showUserDashboard(user);
      }
    }

    function addProduct() {
      const name = document.getElementById('productName').value.trim();
      const price = parseFloat(document.getElementById('productPrice').value);
      const icon = document.getElementById('productIcon').value.trim();

      if (!name || !price || price <= 0) {
        showAlert('productFormAlert', 'Please fill all fields correctly', 'error');
        return;
      }

      const products = getProducts();
      const newId = products.length > 0 ? Math.max(...products.map(p => p.id)) + 1 : 1;

      products.push({
        id: newId,
        name: name,
        price: price,
        icon: icon || '📦'
      });
      saveProducts(products);

      showAlert('productFormAlert', 'Product added successfully!', 'success');
      setTimeout(() => {
        hideAddProductForm();
        showAdminTab('products');
      }, 1000);
    }

    function deleteProduct(productId) {
      if (!confirm('Delete this product?')) return;

      let products = getProducts();
      products = products.filter(p => p.id !== productId);
      saveProducts(products);

      showAdminTab('products');
    }

    // Admin Functions
    function addDailyIncome() {
      if (!confirm('Add $10 to all users?')) return;

      const users = getUsers();
      const transactions = getTransactions();
      let count = 0;

      users.forEach(user => {
        if (user.role !== 'admin') {
          user.balance += 10;
          user.totalRecharge += 10;
          transactions.push({
            mobile: user.mobile,
            type: 'daily_income',
            amount: 10,
            balanceAfter: user.balance,
            date: new Date().toISOString()
          });
          count++;
        }
      });

      saveUsers(users);
      saveTransactions(transactions);

      alert(`Added $10 to ${count} users!`);
      showAdminDashboard();
    }

    function deleteUser(mobile) {
      if (!confirm(`Delete user ${mobile}?`)) return;

      let users = getUsers();
      users = users.filter(u => u.mobile !== mobile);
      saveUsers(users);

      let transactions = getTransactions();
      transactions = transactions.filter(t => t.mobile !== mobile);
      saveTransactions(transactions);

      let orders = getOrders();
      orders = orders.filter(o => o.mobile !== mobile);
      saveOrders(orders);

      showAdminDashboard();
    }

    // Display Functions
    function showUserDashboard(user) {
      document.getElementById('authPage').classList.add('hidden');
      document.getElementById('adminDashboard').classList.add('hidden');
      document.getElementById('userDashboard').classList.remove('hidden');

      document.getElementById('userMobile').textContent = user.mobile;
      document.getElementById('userBalance').textContent = user.balance.toFixed(2);

      displayProducts();
      displayUserOrders();
      displayUserTransactions();
    }

    function displayProducts() {
      const products = getProducts();
      const grid = document.getElementById('productsGrid');

      grid.innerHTML = products.map(p => `
        <div class="product-card">
          <div class="product-image">${p.icon}</div>
          <div class="product-name">${p.name}</div>
          <div class="product-price">$${p.price}</div>
          <button class="btn btn-success" onclick="buyProduct(${p.id})">Buy</button>
        </div>
      `).join('');
    }

    function displayUserOrders() {
      const currentMobile = localStorage.getItem('currentUser');
      const orders = getOrders().filter(o => o.mobile === currentMobile).reverse();
      const div = document.getElementById('userOrders');

      if (orders.length === 0) {
        div.innerHTML = '<p style="text-align: center; color: #6b7280;">No orders yet</p>';
      } else {
        div.innerHTML = orders.map(o => {
          const date = new Date(o.date).toLocaleString();
          return `
            <div class="transaction-item">
              <div>
                <div class="transaction-type">${o.productName}</div>
                <div class="transaction-date">${date}</div>
              </div>
              <div>
                <span class="badge badge-success">${o.status}</span>
                <span style="font-weight: bold; margin-left: 10px;">$${o.price}</span>
              </div>
            </div>
          `;
        }).join('');
      }
    }

    function displayUserTransactions() {
      const currentMobile = localStorage.getItem('currentUser');
      const transactions = getTransactions().filter(t => t.mobile === currentMobile).reverse();
      const div = document.getElementById('userTransactions');

      if (transactions.length === 0) {
        div.innerHTML = '<p style="text-align: center; color: #6b7280;">No transactions yet</p>';
      } else {
        div.innerHTML = transactions.map(t => {
          const isPositive = ['recharge', 'daily_income', 'admin_credit'].includes(t.type);
          const sign = isPositive ? '+' : '-';
          const color = isPositive ? 'positive' : 'negative';
          const date = new Date(t.date).toLocaleString();

          return `
            <div class="transaction-item">
              <div>
                <div class="transaction-type">${t.type.replace('_', ' ')}${t.product ? ': ' + t.product : ''}</div>
                <div class="transaction-date">${date}</div>
              </div>
              <div class="transaction-amount ${color}">${sign}$${t.amount.toFixed(2)}</div>
            </div>
          `;
        }).join('');
      }
    }

    function showAdminDashboard() {
      document.getElementById('authPage').classList.add('hidden');
      document.getElementById('userDashboard').classList.add('hidden');
      document.getElementById('adminDashboard').classList.remove('hidden');

      updateAdminStats();
      displayAdminUsers();
      displayAdminProducts();
      displayAdminOrders();
    }

    function updateAdminStats() {
      const users = getUsers().filter(u => u.role !== 'admin');
      const orders = getOrders();

      const totalBalance = users.reduce((sum, u) => sum + u.balance, 0);
      const totalSales = orders.reduce((sum, o) => sum + o.price, 0);

      document.getElementById('totalUsers').textContent = users.length;
      document.getElementById('totalBalance').textContent = totalBalance.toFixed(2);
      document.getElementById('totalOrders').textContent = orders.length;
      document.getElementById('totalSales').textContent = totalSales.toFixed(2);
    }

    function displayAdminUsers() {
      const users = getUsers().filter(u => u.role !== 'admin');
      const tbody = document.getElementById('usersTableBody');

      if (users.length === 0) {
        tbody.innerHTML = `
          <tr>
            <td colspan="6" style="text-align: center; padding: 40px; color: #6b7280;">
              No users registered yet
            </td>
          </tr>
        `;
      } else {
        tbody.innerHTML = users.map(u => {
          const registered = new Date(u.createdAt).toLocaleDateString();
          const lastLogin = u.lastLogin ? new Date(u.lastLogin).toLocaleDateString() : 'Never';
          const userOrders = getOrders().filter(o => o.mobile === u.mobile).length;

          return `
            <tr>
              <td><strong>${u.mobile}</strong></td>
              <td><span class="badge badge-success">$${u.balance.toFixed(2)}</span></td>
              <td>${userOrders}</td>
              <td>${registered}</td>
              <td>${lastLogin}</td>
              <td>
                <button class="btn btn-danger" style="padding: 6px 12px; font-size: 14px;" onclick="deleteUser('${u.mobile}')">Delete</button>
              </td>
            </tr>
          `;
        }).join('');
      }
    }

    function displayAdminProducts() {
      const products = getProducts();
      const orders = getOrders();
      const tbody = document.getElementById('productsTableBody');

      tbody.innerHTML = products.map(p => {
        const productOrders = orders.filter(o => o.productId === p.id).length;

        return `
          <tr>
            <td style="font-size: 32px;">${p.icon}</td>
            <td><strong>${p.name}</strong></td>
            <td>$${p.price}</td>
            <td>${productOrders}</td>
            <td>
              <button class="btn btn-danger" style="padding: 6px 12px; font-size: 14px;" onclick="deleteProduct(${p.id})">Delete</button>
            </td>
          </tr>
        `;
      }).join('');
    }

    function displayAdminOrders() {
      const orders = getOrders().reverse();
      const tbody = document.getElementById('ordersTableBody');

      if (orders.length === 0) {
        tbody.innerHTML = `
          <tr>
            <td colspan="6" style="text-align: center; padding: 40px; color: #6b7280;">
              No orders yet
            </td>
          </tr>
        `;
      } else {
        tbody.innerHTML = orders.map(o => {
          const date = new Date(o.date).toLocaleString();

          return `
            <tr>
              <td>#${o.id}</td>
              <td>${o.mobile}</td>
              <td>${o.productName}</td>
              <td>$${o.price}</td>
              <td><span class="badge badge-success">${o.status}</span></td>
              <td>${date}</td>
            </tr>
          `;
        }).join('');
      }
    }

    // Tab Functions
    function showUserTab(tab) {
      document.querySelectorAll('.nav-tab').forEach(t => t.classList.remove('active'));
      event.target.classList.add('active');

      document.getElementById('productsTab').classList.add('hidden');
      document.getElementById('ordersTab').classList.add('hidden');
      document.getElementById('transactionsTab').classList.add('hidden');

      document.getElementById(tab + 'Tab').classList.remove('hidden');
    }

    function showAdminTab(tab) {
      document.querySelectorAll('.nav-tab').forEach(t => t.classList.remove('active'));
      event.target.classList.add('active');

      document.getElementById('adminUsersTab').classList.add('hidden');
      document.getElementById('adminProductsTab').classList.add('hidden');
      document.getElementById('adminOrdersTab').classList.add('hidden');

      document.getElementById('admin' + tab.charAt(0).toUpperCase() + tab.slice(1) + 'Tab').classList.remove('hidden');
    }

    // UI Helper Functions
    function showLogin() {
      document.getElementById('loginForm').classList.remove('hidden');
      document.getElementById('registerForm').classList.add('hidden');
      clearAlerts();
    }

    function showRegister() {
      document.getElementById('loginForm').classList.add('hidden');
      document.getElementById('registerForm').classList.remove('hidden');
      clearAlerts();
    }

    function showRechargeForm() {
      document.getElementById('rechargeForm').classList.remove('hidden');
    }

    function hideRechargeForm() {
      document.getElementById('rechargeForm').classList.add('hidden');
      document.getElementById('rechargeAlert').innerHTML = '';
    }

    function showWithdrawForm() {
      document.getElementById('withdrawForm').classList.remove('hidden');
    }

    function hideWithdrawForm() {
      document.getElementById('withdrawForm').classList.add('hidden');
      document.getElementById('withdrawAlert').innerHTML = '';
      document.getElementById('withdrawAmount').value = '';
    }

    function showAddProductForm() {
      document.getElementById('addProductForm').classList.remove('hidden');
    }

    function hideAddProductForm() {
      document.getElementById('addProductForm').classList.add('hidden');
      document.getElementById('productFormAlert').innerHTML = '';
      document.getElementById('productName').value = '';
      document.getElementById('productPrice').value = '';
      document.getElementById('productIcon').value = '';
    }

    function showAlert(elementId, message, type) {
      const alertClass = type === 'success' ? 'alert-success' : 'alert-error';
      document.getElementById(elementId).innerHTML = `
        <div class="alert ${alertClass}">${message}</div>
      `;
    }

    function clearAlerts() {
      ['loginAlert', 'registerAlert', 'rechargeAlert', 'withdrawAlert', 'productFormAlert'].forEach(id => {
        const element = document.getElementById(id);
        if (element) element.innerHTML = '';
      });
    }

    // Initialize on page load
    window.onload = function() {
      initStorage();

      const currentUser = getCurrentUser();
      if (currentUser) {
        if (currentUser.role === 'admin') {
          showAdminDashboard();
        } else {
          showUserDashboard(currentUser);
        }
      }
    };
  </script>
</body>
</html>
