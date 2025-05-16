<!DOCTYPE html>
<html>
<head>
    <title>Merchant Search</title>
</head>
<body>
    <h2>Search by Merchant External ID</h2>
    <input type="text" id="uid" placeholder="Enter ID">
    <button onclick="search()">Search</button>
    <pre id="result"></pre>

    <script>
        async function search() {
            const uid = document.getElementById('uid').value;
            const res = await fetch(`/api/search?uid=${uid}`);
            const data = await res.json();
            document.getElementById('result').textContent = JSON.stringify(data, null, 2);
        }
    </script>
</body>
</html>
