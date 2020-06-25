<template>
    <div>


        <div id="emptystate" class="empty-state animate__animated animate__bounceIn">
            <div id="emptystatecontainer" class="empty-state-container" :class="vmClass">
                <div class="row">
                    <div class="col s12">
                        <span v-if="icon != undefined && icon != null && icon != ''"
                              id="emptystateicon"
                              class="material-icons grey-text empty-state-icon" :style="'font-size:' +  iconSize + 'px'">{{icon}}</span>
                    </div>
                </div>

                <div class="row">
                    <div class="col s12">
                        <strong v-if="label != undefined && label != null && label != ''"
                                id="emptystatelabel"
                                class="empty-state-label">{{label}}</strong>
                        <p v-if="description != undefined && description != null && description != ''"
                           id="emptystatedescription"
                           class="empty-state-description">{{description}}</p>
                    </div>
                </div>

                <slot></slot>
            </div>
        </div>

        <!-- Compiled and minified JavaScript -->
        <script src="https://cdnjs.cloudflare.com/ajax/libs/materialize/1.0.0/js/materialize.min.js">
        </script>
    </div>
</template>



<script>

    export default {
        name: "EmptyState",
        props: {
            vmIcon: {
                type: String,
                default: null,
            },

            vmLabel: {
                type: String,
                default: null,
            },

            vmDescription: {
                type: String,
                default: null,
            },

            vmRounded: {
                type: Boolean,
                default: false,
            },

            vmClass: {
                type: String,
                default: '',
            },

            vmIconSize: {
                type: Number,
                default: 420,
            }
        },
        data() {
            return {
                icon: this.vmIcon,
                label: this.vmLabel,
                description: this.vmDescription,
                rounded: this.vmRounded,
                iconSize: this.vmIconSize,
            }
        },
        mounted() {
            this.M = window.M
        }
    }
</script>

<style>
    .empty-state {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        text-align: center;
        max-width: 420px;
        padding: 36px;
        margin: 0 auto;
        position: relative;
    }

    .empty-state-container {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        text-align: center;
    }

    .empty-state-label {
        font-size: 26px;
        font-weight: 500;
        line-height: 40px;
    }

    .empty-state-description {
        margin: 1em 0;
        font-size: 16px;
        line-height: 24px;
    }
</style>
