<template>
    <div class="ToDo">
        <div class="ToDo__header">
            <img class="ToDo__header-logo" src="../assets/logo/logo.svg" />
            <p class="ToDo__header-welcome">{{ `С возвращением, ${currentUser}!` }}</p>
            <div class="ToDo__header-search">
                <input type="text" class="ToDo__header-search-input">
                <img src="../assets/icons/search.svg" alt="search" class="ToDo__header-search-icon">
            </div>
            <nav class="ToDo__header-navigation">
                <ul class="ToDo__header-navigation-list">
                    <li class="ToDo__header-navigation-list-item">Список</li>
                    <li class="ToDo__header-navigation-list-item"><router-link to="settings/">Настройки</router-link></li>
                    <li class="ToDo__header-navigation-list-item">Сменить аккаунт</li>
                </ul>
            </nav>
        </div>
    </div>
</template>

<script>
export default {
    name: "Header",
    props: ['userName'],
    data(){
        return {
            currentUser: this.userName,
        }
    },
    mounted(){
        
    }
}
</script>

<style lang="scss">
.ToDo {
    font-family: 'Roboto';

    &__header {
        background: rgb(53, 73, 94);
        height: 80px;
        display: flex;
        align-items: center;
        justify-content: space-between;
        padding: 0px 40px;

        &-welcome {
            font-size: 24px;
            font-weight: 700;
            margin-left: 40px;
            color: white;
        }

        &-search {
            position: relative;

            &-input {
                font-size: 18px;
                border-radius: 10px;
                padding: 0px 40px 0px 10px;
                height: 40px;
            }

            &-icon {
                position: absolute;
                top: 10px;
                right: 10px;
                width: 22px;
                height: 22px;
                cursor: pointer;
                transition: transform 0.3s cubic-bezier(0.175, 0.885, 0.32, 1.275);

                &:hover {
                    transform: scale(1.2);
                }
            }
        }

        &-navigation {
            &-list {
                display: flex;

                &-item {
                    margin-left: 40px;
                    font-size: 24px;
                    color: white;
                    cursor: pointer;

                    &:hover {
                        color: rgb(65, 184, 131);
                        text-decoration: underline;
                    }
                }
            }
        }
    }

}</style>