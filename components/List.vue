<template>
    <div class="content__list">
        <div v-for="item in arr" :key="item.lvl" class="content__item">
            <table class="content__item-header">
                <thead>
                    <tr>
                        <td class="content__item-header-number">{{item.lvl}}</td>
                        <td class="content__item-header-number">{{item.activePartners}}</td>
                    </tr>
                </thead>

                <tbody>
                    <tr>
                        <td class="content__item-header-text">Уровень выплат</td>
                        <td class="content__item-header-text">Активных партнёров</td>
                    </tr>
                </tbody>
            </table>

            <div class="content__item-list">
                <a v-for="i in item.users" :key="i" href="#" class="content__item-user">
                    <div class="content__item-user-img-wrap">
                        <img src="@/assets/img/woman.png" alt="woman">
                    </div>

                    <div class="content__item-user-name">kris_anfalova</div>
                </a>
            </div>
        </div>
    </div>
</template>

<script>
export default {
  name: 'List',
  data: () => ({
    arr: [
        {
            lvl: 1,
            activePartners: 133,
            users: 4
        },
        {
            lvl: 2,
            activePartners: 129,
            users: 10
        },
        {
            lvl: 3,
            activePartners: 5455,
            users: 10
        },
        {
            lvl: 4,
            activePartners: 4500,
            users: 10
        },
        {
            lvl: 5,
            activePartners: 43233,
            users: 10
        },
        {
            lvl: 6,
            activePartners: 4500,
            users: 10
        },
        {
            lvl: 7,
            activePartners: 43233,
            users: 10
        },
        {
            lvl: 8,
            activePartners: 133,
            users: 10
        },
        {
            lvl: 9,
            activePartners: 129,
            users: 10
        },
        {
            lvl: 10,
            activePartners: 5455,
            users: 10
        },
        {
            lvl: 11,
            activePartners: 4500,
            users: 10
        },
        {
            lvl: 12,
            activePartners: 43233,
            users: 10
        },
        {
            lvl: 13,
            activePartners: 4500,
            users: 10
        },
        {
            lvl: 14,
            activePartners: 43233,
            users: 10
        },
    ]
  }),
}
</script>

<style lang="scss">
.content {
    &__list {
        margin-top: 147px;
        padding-left: 50px;
        display: flex;
        flex-wrap: wrap;
        align-items: flex-start;
        justify-content: flex-start;
        gap: 35px;
    }

    &__item {
        background: #1E273A;
        border-radius: 20px;
        padding: 15px 15px 20px;
        width: 119px;
        transition: all .3s;

        &:hover,
        &:focus {
            transition: all .3s;
            filter: drop-shadow(0px 4px 4px rgba(0, 0, 0, 0.25));
        }

        &-header {
            tr td:first-child {
                width: 43px;
            }

            thead tr {
                box-shadow: 0px 1px 0px 0 #2e384c;
            }

            &-text {
                font-size: 8px;
                line-height: 10px;
            }
        }

        &-list {
            margin-top: 23px;
            height: 130px;
            overflow-y: auto;

            &::-webkit-scrollbar {
                width: 1px;
            }
            &::-webkit-scrollbar-track {
                border: 1px solid #192233;
                border-radius: 15px;
            }
            &::-webkit-scrollbar-thumb {
                background: #707D96;
                border-radius: 15px;
            }
        }

        &-user {
            opacity: 0.5;
            display: flex;
            align-items: center;
            transition: all .3s;

            &:not(:last-child) {
                margin-bottom: 10px;
            }

            &-img-wrap {
                width: 25px;
                height: 25px;
                border-radius: 50%;
                border: 1px solid #DCE0F4;

                img {
                    width: 100%;
                    border-radius: 50%;
                }
            }

            &-name {
                font-size: 8px;
                line-height: 10px;
                margin-left: 5px;
            }

            &:hover,
            &:focus {
                opacity: 1;
                transition: all .3s;
            }
        }
    }
}

@media screen and (max-width: 992px) {
  .content__list {
    margin-top: 30px;
    padding-left: 0;
  }
}

@media screen and (max-width: 780px) {
  .content__list {
    margin-top: 30px;
    padding-left: 0;
  }
}

@media screen and (max-width: 576px) {
  .content__list {
    gap: 10px;
}
}
</style>