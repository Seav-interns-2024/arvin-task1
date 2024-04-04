<script>
export default {
    data() {
        return {
            firstName: '',
            middleName: '',
            lastName: '',
            suff: '',
            contactNum: '',
            bday: '',
            age: '',
            gender: '',
            email: '',
            password: '',
            terms: false,
            passwordError: '',
        }
    },
    methods: {
        handleSubmit() {
            this.passwordError = this.password.length > 5 ? '' 
            : 'Password must be more than 5 characters'

            if (this.terms = true) {
                this.terms = 'Accepted'
            } 

            if(!this.passwordError) {
                console.log('Firstname: ', this.firstName)
                console.log('Middlename: ', this.middleName)
                console.log('Lastname: ', this.lastName)
                console.log('Suffix: ', this.suff)
                console.log('Contact Number: ', this.contactNum)
                console.log('BirthDay: ', this.bday)
                console.log('Age: ', this.age)
                console.log('Gender: ', this.gender)
                console.log('Email: ', this.email)
                console.log('Password: ', this.password)
                console.log('Terms: ', this.terms)
                this.$router.push('/home');
                alert('Welcome to Straw Hats '+ this.firstName + ' ' + this.suff)
            }
        }
    }
}
</script>

<template>
    <div class="flex flex-col md:flex-row justify-center items-center h-screen">
        <div class="w-full md:w-1/3 flex justify-center">
            <img src="/assets/images/asl.png" class="h-13 w-auto" alt="Main Logo">
        </div>
        <div class="w-full md:w-2/3 flex justify-center" id="component">
            <form @submit.prevent="handleSubmit">
                <div class="w-full md:w-3/4 lg:w-11/12 bg-gray-200 p-4 rounded-lg">
                    <div class="flex flex-wrap justify-between">
                        <div class="flex-1 mb-4 mr-4">
                            <label>FIRST NAME</label>
                            <input type="text" v-model="firstName" required
                                class="block border rounded-md w-full px-2 py-1 mb-2">
                        </div>
                        <div class="flex-1 mb-4 mr-4">
                            <label>MIDDLE NAME</label>
                            <input type="text" v-model="middleName"
                                class="block border rounded-md w-full px-2 py-1 mb-2">
                        </div>
                        <div class="flex-1 mb-4 mr-4">
                            <label>LAST NAME</label>
                            <input type="text" v-model="lastName" required
                                class="block border rounded-md w-full px-2 py-1 mb-2">
                        </div>
                        <div class="flex-1 mb-4">
                            <label>SUFFIX</label>
                            <select v-model="suff" class="block border rounded-md w-full px-2 py-1 mb-2">
                                <option value=" "> </option>
                                <option value="Jr.">JR</option>
                                <option value="Sr.">SR</option>
                            </select>
                        </div>
                    </div>
                    <div class="flex flex-wrap justify-between">
                        <div class="flex-1 mb-4 mr-4">
                            <label>CONTACT NUMBER</label>
                            <input type="text" v-model="contactNum" required
                                class="block border rounded-md w-full px-2 py-1 mb-2">
                        </div>
                        <div class="flex-1 mb-4 mr-4">
                            <label>DATE OF BIRTH</label>
                            <input type="date" v-model="bday" required
                                class="block border rounded-md w-full px-2 py-1 mb-2">
                        </div>
                        <div class="flex-1 mb-4 mr-4">
                            <label>AGE</label>
                            <input type="text" v-model="age" required
                                class="block border rounded-md w-full px-2 py-1 mb-2">
                        </div>
                        <div class="flex-1 mb-4">
                            <label>GENDER</label>
                            <select v-model="gender" class="block border rounded-md w-full px-2 py-1 mb-2">
                                <option value=" "> </option>
                                <option value="MALE">MALE</option>
                                <option value="FEMALE">FEMALE</option>
                                <option value="LGBTQ+">LGBTQ+</option>
                                <option value="N/A">Prefer not to say</option>
                            </select>
                        </div>
                    </div>
                    <div class="flex flex-wrap justify-between">
                        <div class="flex-1 mb-4 mr-4">
                            <label>Email</label>
                            <input type="email" v-model="email" required class="block border rounded-md w-full px-2 py-1 mb-2">
                        </div>
                        <div class="flex-1 mb-4">
                            <label>Password</label>
                            <input type="password" v-model="password" required class="block border rounded-md w-full px-2 py-1 mb-2">
                            <div v-if="passwordError" class="text-red-500">{{ passwordError }}</div>
                        </div>
                    </div>
                    <div class="flex items-center mb-12">
                        <input type="checkbox" v-model="terms" required class="mr-2">
                        <label>Data Privacy Consent</label>
                    </div>
                    <div class="flex justify-center mb-4 ">
                        <button class="block border border-yellow-600 text-yellow-600 rounded-md w-1/2 px-2 py-1 
                    hover:bg-yellow-600 hover:text-white hover:border-yellow-600 transition-colors">SIGN UP</button>
                    </div>
                </div>
            </form>
        </div>
    </div>
</template>

<style scoped>
@media screen and (max-width: 768px) {
    .flex-col {
        flex-direction: column;
    }

    .w-full {
        width: 100%;
    }
}
</style>