<template>
    <div class="page-checkout">
        <div class="columns is-multiline">
            <div class="column is-12">
                <h1 class="title">Checkout</h1>
            </div>

            <div class="column is-12 box">
                <table class="table is-fullwidth" v-if="cartTotalLength">
                    <thead>
                        <tr>
                            <th>Product</th>
                            <th>Price</th>
                            <th>Quantity</th>
                            <th>Total</th>
                        </tr>
                    </thead>

                    <tbody>
                        <tr v-for="item in cart.items" v-bind:key="item.product.id">
                            <td>{{ item.product.name }}</td>
                            <td>ETB {{ item.product.price }}</td>
                            <td>{{ item.quantity }}</td>
                            <td>ETB {{ getItemTotal(item).toFixed(2) }}</td>
                        </tr>
                    </tbody>

                    <tfoot>
                        <tr>
                            <td colspan="2">Total</td>
                            <td>{{ cartTotalLength }}</td>
                            <td>ETB {{ cartTotalPrice.toFixed(2) }}</td>
                        </tr>
                    </tfoot>
                </table>
            </div>

            <div class="column is-12 box">
                <h2 class="subtitle">Shipping Details</h2>

                <p class="has-text-grey mb-4">* Required fields</p>

                <div class="columns is-multiline">
                    <div class="column is-6">
                        <div class="field">
                            <label>First Name*</label>
                            <div class="control">
                                <input type="text" class="input" v-model="first_name">
                            </div>
                        </div>

                        <div class="field">
                            <label>Last Name*</label>
                            <div class="control">
                                <input type="text" class="input" v-model="last_name">
                            </div>
                        </div>

                        <div class="field">
                            <label>E-mail*</label>
                            <div class="control">
                                <input type="email" class="input" v-model="email">
                            </div>
                        </div>

                        <div class="field">
                            <label>Phone*</label>
                            <div class="control">
                                <input type="tel" class="input" v-model="phone">
                            </div>
                        </div>
                    </div>

                    <div class="column is-6">
                        <div class="field">
                            <label>Address*</label>
                            <div class="control">
                                <input type="text" class="input" v-model="address">
                            </div>
                        </div>

                        <div class="field">
                            <label>Zip Code</label>
                            <div class="control">
                                <input type="number" class="input" v-model="zipcode">
                            </div>
                        </div>

                        <div class="field">
                            <label>Place</label>
                            <div class="control">
                                <input type="text" class="input" v-model="place">
                            </div>
                        </div>
                    </div>
                </div>

                <div class="notification is-danger" v-if="errors.length">
                        <p v-for="error in errors" v-bind:key="error">{{ error }}</p>
                    </div>

                    <hr>

                    <div id="card-element" class="mb-5">

                    </div>

                    <template v-if="cartTotalLength">
                        <hr>

                        <button class="button is-dark" @click="submitForm">Pay with Telebirr</button>
                    </template>
            </div>
        </div>
    </div>
</template>

<script>
import axios from 'axios'

export default {
    name: 'Checkout',
    data() {
        return {
            cart: {
                items: []
            },
            stripe: {},
            card: {},
            first_name: '',
            last_name: '',
            email: '',
            phone: '',
            address: '',
            zipcode: '',
            place: '',
            errors: []
        }
    },
    mounted() {
        document.title = 'Checkout | Zute Mart'

        this.cart = this.$store.state.cart
    },
    methods: {
        getItemTotal(item) {
            return item.quantity * item.product.price
        },
        submitForm() {
            this.errors = []

            if (this.first_name === '') {
                this.errors.push('First name is missing')
            }

            if (this.last_name === '') {
                this.errors.push('Last name is missing')
            }

            if (this.email === '') {
                this.errors.push('Email is missing')
            }

            if (this.phone === '') {
                this.errors.push('Phone number is missing')
            }

            if (this.address === '') {
                this.errors.push('Address is missing')
            }
        }
    },
    computed: {
        cartTotalLength() {
            return this.cart.items.reduce((accumulator, currentVal) => {
                return accumulator += currentVal.quantity
            }, 0)
        },
        cartTotalPrice() {
            return this.cart.items.reduce((accumulator, currentVal) => {
                return accumulator += currentVal.product.price * currentVal.quantity
            }, 0)
        },
    }
}
</script>