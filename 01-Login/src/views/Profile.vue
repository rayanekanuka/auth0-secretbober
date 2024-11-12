<template>
  <div class="container">
    <div class="row align-items-center profile-header">
      <div class="col-md-2 mb-3">
        <img
          :src="user?.picture"
          alt="User's profile picture"
          class="rounded-circle img-fluid profile-picture"
        />
      </div>
      <div class="col-md text-center text-md-left">
        <h2>{{ user?.name }}</h2>
        <p class="lead text-muted">{{ user?.email }}</p>
      </div>
    </div>

    <div class="card-profile">
<!--      <highlightjs language="json" :code="JSON.stringify(user, null, 2)" />-->
      <p>Prénom : {{user?.given_name}}</p>
      <p>Nom : {{user?.family_name}}</p>
      <p>Nickname : {{user?.nickname}}</p>
      <p>Name : {{user?.name}}</p>
      <p>Email : {{user?.email}}</p>
    </div>
  </div>
</template>

<script lang="ts">
import { useAuth0 } from '@auth0/auth0-vue';

export default {
  name: "profile-view",
  setup() {
    const auth0 = useAuth0();
    
    return {
      user: auth0.user,
    }
  }
};
</script>

<style scoped>

.profile-header {
  margin-bottom: 20px;
}

.profile-picture {
  width: 100%;
  max-width: 200px;
}

.card-profile {
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  background-color: #fff;
}

</style>