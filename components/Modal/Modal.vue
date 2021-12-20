<template>
    <div class="modal-wrap">
        <div @click="toggleModal" class="overlay"></div>

        <div class="modal">
            <div @click="toggleModal" class="modal__close">×</div>

            <div class="modal__title">Всегда на связи!</div>

            <div class="modal__input-wrap">
                <label for="title" class="modal__input-title-label">Тема</label>

                <input id="title" type="text" class="modal__input-title">
            </div>

            <div class="modal__input-wrap">
                <label for="description" class="modal__input-text-label">Описание</label>

                <textarea id="description" class="modal__input-text" />
            </div>

            <button class="btn btn_modal">Отправить</button>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Modal',
    methods: {
        toggleModal() {
            this.$emit('toggleModal', false)
        }
    }
}
</script>

<style lang="scss">
.overlay {
  position: fixed;
  height: 100vh;
  width: 100vw;
  right: 0;
  top: 0;
  background: #192233;
  opacity: .8;
}

.modal {
    position: absolute;
    z-index: 10;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    display: flex;
    flex-direction: column;
    max-width: 300px;
    width: 100%;
    background: #131b29;
    padding: 10px;
    border-radius: 10px;

    &-wrap {
        left: 0;
        top: 0;
        width: 100%;
        height: 100%;
        position: fixed;
        overflow: hidden;
        z-index: 10;
    }

    &__title {
        font-size: 16px;
        line-height: 24px;
        text-align: center;
    }

    &__input {
        &-wrap {
            margin-top: 20px;
            display: flex;
            flex-direction: column;
        }

        &-title,
        &-text {
            outline: none;
            color: #192233;
            padding: 5px;
            border-radius: 5px;
        }

        &-text {
            height: 100px;
            resize: none;

            &::-webkit-scrollbar {
                width: 3px;
            }
            &::-webkit-scrollbar-track {
                border: 3px solid #192233;
                border-radius: 15px;
            }
            &::-webkit-scrollbar-thumb {
                background: #707D96;
                border-radius: 15px;
            }
        }
    }

    &__close {
        position: absolute;
        font-size: 24px;
        cursor: pointer;
        right: 5px;
        top: 5px;
    }
}
</style>