<template>
  <div>
    <p>
      When get cookie data, expire date change to session
    </p>
    <button @click="setCookie">Set Cookie</button>
    <button @click="getCookieData">Get Data</button>
  </div>
</template>

<script setup lang="ts">

const getCookieData = () => {
  const cookie = useCookie("test-cookie", { watch: false });
  if (cookie.value)
    alert(`data = ${cookie.value} | refresh browser and check cookie expire date`);
  else
    alert('cookie not found')
}

const setCookie = () => {
  const testCookie = useCookie("test-cookie", {
    expires: new Date(new Date().setDate(new Date().getDate() + 30)),
  });
  testCookie.value = "mohammad ashrafi"
}
</script>
