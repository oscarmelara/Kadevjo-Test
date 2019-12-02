<template id="slidemenu">
  <div class="w-full bg-white fixed menu block lg:hidden border-b border-gray-300 z-50">
        <div class="w-1/2 flex justify-start items-center my-2">
           <router-link to="/profile"><img class="w-48 mr-16 px-5 lg:px-0" src="@/assets/images/logo-menu.png" alt></router-link>
        </div>
        <div class="pointer" :class="['menu__burger', {'menu__burger--open': this.open}] " @click="toggleNav">
            <span class="menu__burger__span"></span>
        </div>

        <nav class="h-screen bg-white fixed top-0 left-0 w-screen" :class="['menu__nav', {'menu__nav--open': this.open}]">
          <div class="menu-container py-4 flex w-full h-full justify-center items-center">
            <ul class="menu-wrapper text-2xl mx-0 my-auto">
              <li @click="setActiveClass" class="menu-item py-2 text-gray-700 text-left font-semibold">
                <router-link to="/profile">Option</router-link>
              </li>
              
              <li @click="setActiveClass" class="menu-item py-2 text-gray-700 text-left font-semibold">
                <router-link to="/search">Option</router-link>
              </li>
              <li @click="setActiveClass" class="menu-item py-2 text-gray-700 text-left font-semibold">
                <router-link to="/chat">Option</router-link>
              </li>
              <li @click="setActiveClass" class="menu-item py-2 text-gray-700 text-left font-semibold">
                <router-link to="/support">Option</router-link>
              </li>
              <li @click="setActiveClass" class="menu-item py-2 text-gray-700 text-left font-semibold">
                <router-link class="flex items-center" to="/subscriptions"><img class="mr-2 h-5" src="@/assets/images/profile.svg" alt=""> Iniciar sesion</router-link>
              </li>
              
            </ul>
          </div>
        </nav>
    </div>
</template>

<script>
import { mapActions } from "vuex";

export default {
  name: 'SliderMenu',
  template: "#slidemenu",
  data: () =>  ({
    open: false,
    items: [
      { name: 'Home', to: '/' },

    ]
  }),
  methods: {
    // ...mapActions("auth", ["logout"]),
    // async handleLogout() {
    //   await this.logout();
    //   this.$router.replace({ name: "login" });
    // },
    toggleNav: function() {
            this.open = !this.open;
            this.$emit('toggle', this.open);

            if(this.open) {
              document.body.style.overflow = 'hidden';
            }

            document.body.style.overflow = 'auto';

    },
    showDrop(){
      document.getElementById("myDropdown").classList.toggle("show_list");
    },
    toogleActiveClass(e) {
      const {target} = e;

      if(e.target.classList.contains('active')) {
        e.target.classList.remove('active');
        return;

      }

      Array.from(document.querySelectorAll('.has-dropdown .dropdown-trigger')).forEach(item => item.classList.remove('active'));


      e.target.classList.add('active');
    },
    setActiveClass(e) {
      const {target} = e;
      const activeClass = 'active-link';
      Array.from(document.querySelectorAll('.menu-item .active-link')).forEach(item => item.classList.remove(activeClass))

      target.classList.add(activeClass);

      this.open = !this.open;
    }
  }
}
</script>
<style lang="scss">

.menu-container {
  .menu-item {
    &:hover,
    & .active-link {
      color: #1d42b1;
    }
  }

  .has-dropdown {
    .sub-menu-wrapper {
      max-height: 0;
      overflow: hidden;
      -webkit-transition: all 0.5s ease-in-out;
      -moz-transition: all 0.5s ease-in-out;
      -o-transition: all 0.5s ease-in-out;
      transition: all 0.5s ease-in-out;
    }

    .dropdown-trigger.active {
      color: #1d42b1;
    }
    .dropdown-trigger.active~ .sub-menu-wrapper {
      max-height: 500px;
    }

    .drop-arrow {
      font-size: .6em;
      color: #1d42b1;
      padding-left: 1em;
    }
  }
}
.show_list {display: flex!important;}
.dropdown-content {
  display: none;
}

.menu {
    $root: &;

	&__burger {
		$burger: #{$root}__burger;
		width: 40px;
		right: 20px;
		top: 25px;
		position: fixed;
		cursor: pointer;
		z-index: 200;

		&__span {
			position: absolute;
			height: 3px;
			width: inherit;
			background-color: #0669f9;
			transition: all 0.2s;
			&:before {
				@extend #{$burger}__span;
				content: "";
				top: -10px;
			}
			&:after {
				@extend #{$burger}__span;
				content: "";
				top: 10px;
			}
		}
		&--open {
			#{$burger}__span {
				background-color: transparent;
				&:before, &:after {
					background-color: #0669f9;
					transform-origin: 0 50%;
				}
				&:before {
					transform: translateX(7px) translateY(-5px) rotate(45deg);
				}
				&:after {
					transform: translateX(7px) translateY(3px) rotate(-45deg);
				}
			}
		}
	}

}

.menu__nav {
  transform: translateX(-100%);
  transition: all 0.3s;
  z-index: 100;
  &--open {
    display: inline-grid;
    overflow: scroll;
    transform: translateX(0);
  }

}

</style>
