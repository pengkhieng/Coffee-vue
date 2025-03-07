<template>
    <div class="min-h-screen flex items-center bg-gray-100">
        <div class="bg-white p-8 w-full max-w-md align-top rounded-lg shadow-lg  h-screen">
            <div class="flex justify-center mb-6 pb-4">
                <img alt="Vue logo" class="logo" src="@/assets/logo.png" width="125" height="125" />
            </div>
            <h2 class="text-2xl font-bold mb-6 text-center text-black pb-4">Login to your account</h2>
            <form @submit.prevent="handleLogin" class="space-y-6">
                <div class="pb-4">
                    <label for="username" class="block text-sm font-medium text-gray-700 pb-2">Username</label>
                    <input type="text" id="username" v-model="username" required
                        class="mt-1 block w-full px-3 py-2 border border-gray-300 rounded-md shadow-sm focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm" />
                </div>
                <div class="pb-4">
                    <label for="password" class="block text-sm font-medium text-gray-700 pb-2">Password</label>
                    <input type="password" id="password" v-model="password" required
                        class="mt-1 block w-full px-3 py-2 border border-gray-300 rounded-md shadow-sm focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm pt-4" />
                </div>
                <div class="flex items-center justify-between pb-2">
                    <div class="flex items-center">
                        <input type="checkbox" id="rememberMe" v-model="rememberMe"
                            class="h-4 w-4 text-indigo-600 focus:ring-indigo-500 border-gray-300 rounded" />
                        <label for="rememberMe" class="ml-2 block text-sm text-gray-900 pl-2">Remember me</label>
                    </div>
                </div>
                <div>
                    <button type="submit"
                        class="w-full flex justify-center py-2 px-4 border border-transparent rounded-md shadow-sm text-sm font-medium text-white bg-indigo-600 hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500">Sign
                        In</button>
                </div>
            </form>
            <div class="mt-6 pt-4">
                <div class="relative">
                    <div class="absolute inset-0 flex items-center">
                        <div class="w-full border-t border-gray-300"></div>
                    </div>
                    <div class="relative flex justify-center text-sm">
                        <span class="px-2 bg-white text-gray-500">or Login with</span>
                    </div>
                </div>
                <div class="mt-6 grid grid-cols-2 gap-3 pt-4">
                    <button @click="loginWithGoogle"
                        class="w-full inline-flex justify-center py-2 px-4 border border-gray-300 rounded-md shadow-sm bg-white text-sm font-medium text-gray-700 hover:bg-gray-50">
                        📅 Login with Google
                    </button>
                    <button @click="loginWithApple"
                        class="w-full inline-flex justify-center py-2 px-4 border border-gray-300 rounded-md shadow-sm bg-white text-sm font-medium text-gray-700 hover:bg-gray-50">
                        📈 Login with Apple
                    </button>
                </div>
            </div>
            <div class="mt-6 text-center pt-8">
                <p class="text-sm text-gray-600">Don’t have an account? <a href="#"
                        class="font-medium text-indigo-600 hover:text-indigo-500">Create an Account</a></p>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            username: '',
            password: '',
            rememberMe: false
        };
    },
    methods: {
        handleLogin() {
            // Handle login logic here
            if (this.username === 'khieng@gmail.com' && this.password === 'admin') {
                this.$router.push({ name: 'home' });
                alert('Login successfully');
            } else {
                alert('Username or password is incorrect');
            }
        },
        loginWithGoogle() {
            // Handle Google login logic here
            alert('Logging in with Google');
        },
        loginWithApple() {
            // Handle Apple login logic here
            alert('Logging in with Apple');
        }
    }
};
</script>