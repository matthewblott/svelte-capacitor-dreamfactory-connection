<script>
  let base_url = "http://10.0.2.2:8000/api/v2";

  const login = async (email, password) => {
    const headers = new Headers({
      "Content-Type": "application/json",
    });

    const credentials = {
      email: email,
      password: password,
    };

    const body = JSON.stringify(credentials);
    const url = `${base_url}/user/session`;
    const response = await fetch(url, {
      method: "POST",
      headers: headers,
      body,
    });

    if (!response.ok) {
      console.log("error");
      return response.statusText;
    } else {
      console.log("success");
      const json = await response.json();

      return json;
    }
  };
  const connect = async () => {
    const res = await login("read_write@northwi.nd", "password");

    console.log(res);
  };
</script>

<main>
  <h1>Vite + Svelte</h1>

  <button on:click={connect}>Connect</button>
</main>
