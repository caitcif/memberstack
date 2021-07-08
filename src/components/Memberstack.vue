<template>
  <div>
    <div v-show="showingModal === 'signup'">
      sign up form
      <form ms-signup="true">
        <input ms-field="email" />
        <input ms-field="password" />
        <input type="submit" value="Sign up" />
      </form>
    </div>
    <div v-show="showingModal === 'login'">
      login form
      <form ms-login="true">
        <input ms-field="email" />
        <input ms-field="password" />
        <input type="submit" value="login" />
      </form>
    </div>
    <div v-show="false">
      <button ref="profileButton" type="button" ms-profile="true">
        profile
      </button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      showingModal: undefined,
    };
  },
  mounted() {
    const msScript = document.createElement("script");
    msScript.src = "https://api.memberstack.io/static/memberstack.js?custom";
    msScript.setAttribute("data-memberstack-id", "YOUR_ID");
    msScript.onload = () => {
      MemberStack.onReady.then((member) => {
        // store member data wherever you find appropreate
      });
    };
    document.head.append(msScript);
  },
};
</script>
