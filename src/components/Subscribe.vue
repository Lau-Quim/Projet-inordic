<template>
    <div class="subscribe">
        <h2>будь всегда в курсе выгодных предложений</h2>
        <h3>подписывайся и следи за новинками и выгодными предложениями.</h3>
        <form v-show="!showSuccess">
            <input type="email" name="email" v-model="email" placeholder="email"/>
            <button type="submit"
                    :disabled="email.length === 0 || showError"
                    @click="submitSubscribe">
                записаться
            </button>
        </form>
        <div class="subscribe-error" v-show="showError">
            Некорректный email. Попробуйте еще раз
        </div>
        <div class="subscribe-success" v-show="showSuccess">
            Вы успешно подписаны
        </div>
    </div>
</template>

<script>

    export default {
        name: "Subscribe",
        data() {

            return {
                email: '',
                showError: false,
                showSuccess: false
            };
        },
        watch: {
            email( newVal, oldVal ) {

                console.log(oldVal);
                console.log(newVal);

                if (~newVal.indexOf('@') && newVal.indexOf('@') > 0 &&
                    ~newVal.lastIndexOf('.') && newVal.lastIndexOf('.') > newVal.indexOf('@') + 1 &&
                    newVal.lastIndexOf('.') < newVal.length - 1
                ) {
                    this.showError = false;
                } else {
                    this.showError = true;
                }
            }
        },
        methods: {
            submitSubscribe( event ) {

                event.preventDefault();

                if (!!this.email && this.email.length > 0) {

                    const body = JSON.stringify({
                        email: this.email
                    });

                    fetch(
                        'http://192.168.64.2/api/subscribe.php',
                        {
                            method: 'POST',
                            headers: {
                                'Accept': 'application/json',
                                'Content-Type': 'application/json'
                            },
                            mode: 'cors',
                            body
                        }
                    ).then(res => res.json()).then(res => {

                        if (res) {
                            this.showSuccess = true;
                        } else {
                            this.showError = true;
                        }
                    });
                }
            }
        }
    }

</script>

<style scoped>

    .subscribe {
        display: flex;
        align-items: center;
        flex-direction: column;
        margin: 7rem 0;
    }

    .subscribe h2 {
        text-transform: uppercase;
        font-size: 2rem;
        opacity: .8;
        margin-bottom: 10px;
    }

    .subscribe h3 {
        font-style: italic;
        font-size: .9rem;
        margin-top: 0;
        color: grey;
    }

    .subscribe form {
        display: flex;
        align-items: center;
        width: 60%;
        margin: 1rem auto 0;
    }

    .subscribe form input {
        font-style: italic;
        margin-right: 0;
        width: 80%;
        padding: 15px;
        border-width: 1px 0 1px 1px;
        border-color: grey;
        border-style: solid;
    }

    .subscribe form button {
        height: 100%;
        margin-left: 0;
        background-color: orange;
        color: white;
        border: 1px solid orange;
        padding: 15px;
    }

    .subscribe-error, .subscribe-success {
        margin-top: 1rem;
        font-style: italic;
        font-size: .8rem;
    }

    .subscribe-error{
        color: red;
    }

    .subscribe-success{
        color: green;
    }

</style>