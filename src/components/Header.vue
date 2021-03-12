<template>
  <header class="header">
    <div class=" header__left-block">
      <Logo class="header__logo" />
      <p class="header__text">
        World's first affordable airsharing
      </p>
    </div>
    <div class="header__right-block">
      <div class="services">
        <button class="theme__btn">
          <Moon class="theme__icon-btn" />
          <p class="theme__text-btn">Night mod</p>
        </button>
        <button class="message__button">
          <Message class="message__icon" />
        </button>
        <button class="notification__button">
          <Notification class="notification__icon" />
        </button>
      </div>
      <div class="author">
        <p class="author__name">
          Bessie Cooper
        </p>
        <img class="author__icon" src="../assets/images/author.jpg" />
      </div>
    </div>
  </header>
</template>

<script>
import Logo from "./SvgIcons/svgLogotip";
import Moon from "./SvgIcons/svgMoon";
import Message from "./SvgIcons/SvgMessage";
import Notification from "./SvgIcons/SvgNotification";

export default {
  components: {
    Logo,
    Moon,
    Message,
    Notification,
  },
};
</script>

<style lang="scss">
.a {
  position: absolute;
  top: 0;
  left: 16px;

  display: flex;
  justify-content: center;
  align-items: center;

  width: 100px;
  height: 40px;
  border-radius: 59.4746px;

  background: linear-gradient(
    101.66deg,
    #505add 34.4%,
    #be40c0 66.11%,
    #fba82b 96.37%
  );
}
.header {
  display: flex;
  align-items: center;
  justify-content: space-between;

  max-width: 1312px;
  width: 100%;

  margin: 48px auto 40px;

  &__left-block {
    display: flex;
    align-items: center;

    .header__logo {
      margin-right: 64px;
    }

    .header__text {
      font-weight: 300;
      font-size: 16px;
      line-height: 152%;
    }
  }
  &__right-block {
    display: flex;
    align-items: center;

    .services {
      display: flex;
      margin-right: 59px;

      .theme__btn {
        display: flex;
        align-items: center;

        margin-right: 107px;
        padding: 0px;

        background: transparent;
        border: white;

        .theme__icon-btn {
          margin-right: 18px;
          padding: 0px;
        }

        .theme__text-btn {
          font-weight: 300;
          font-size: 16px;
          line-height: 152%;
          color: #677b8f;
        }
      }
      .message__button {
        background: white;
        border: white;

        margin-right: 29px;
        padding: 0px;
      }
      .notification__button {
        background: white;
        border: white;

        padding: 0px;
      }
    }
    .author {
      display: flex;
      align-items: center;

      .author__name {
        font-size: 16px;
        font-weight: bold;
        line-height: 152%;
        color: #012345;

        margin-right: 16px;
      }
      .author__icon {
        margin-right: 10px;
        border-radius: 30px;
      }
    }
  }
}

@media screen and (max-width: 1023px) {
  .header__left-block {
    .header__logo {
      margin-right: 10px;
      width: 100%;
    }
  }
  .header__text {
    display: none;
  }
}
@media screen and (max-width: 767px) {
  .header__right-block {
    .services {
      margin-right: 20px;
      .theme__btn {
        margin-right: 0px;
        .theme__text-btn {
          display: none;
        }
      }
    }
    .author {
      .author__name {
        display: none;
      }
    }
  }
}
@media screen and (max-width: 425px) {
  .header__right-block {
    .services {
      .message__button {
        margin-right: 20px;
      }
    }
    .author {
      .author__icon {
        width: 32px;
      }
    }
  }
}
</style>
