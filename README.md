    const currentUser = JSON.parse(localStorage.getItem("user"));

const userDisplay = document.getElementById("userDisplay");
const loginBtn = document.getElementById("loginBtn");
const registerBtn = document.getElementById("registerBtn");
const adminBtn = document.getElementById("adminBtn");
const logoutBtn = document.getElementById("logoutBtn");

if (currentUser) {
    userDisplay.innerHTML = `Halo, ${currentUser.username} (${currentUser.role}) `;
    
    loginBtn.style.display = "none";
    registerBtn.style.display = "none";
    logoutBtn.style.display = "inline-block";

    if (currentUser.role === "admin") {
        adminBtn.style.display = "inline-block";
    }
} else {
    userDisplay.innerHTML = "";
    loginBtn.style.display = "inline-block";
    registerBtn.style.display = "inline-block";
    adminBtn.style.display = "none";
    logoutBtn.style.display = "none";
}

function handleLogout() {
    localStorage.removeItem("user");
    window.location.reload();
}
    </script>

    <script src="js/auth.js"></script>
