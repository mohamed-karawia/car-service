<template>
  <footer class="footer">
    <div class="footer--items">
      <div class="footer__item">
        <h2>About us</h2>
        <p>
          Donec vel sapien augue. Integer urna turpis cursus porta, mauris
          molestie<br /><br />Cursus sodales vitae suscipit egestas lobortis
          aliquam quaerat hendrerit sapien undo euismod blandit. nulla at
          sodales mollis in hendrerit tellus
        </p>
      </div>
      <div class="footer__item">
        <h2>Repair services</h2>
        <ul class="list--repairs">
          <li><a href="#">Repair Car Engine</a></li>
          <li><a href="#">Repair Car Suspension</a></li>
          <li><a href="#">Auto Brake System</a></li>
          <li><a href="#">Change of oil</a></li>
          <li><a href="#">Alternator </a></li>
        </ul>
      </div>
      <div class="footer__item">
        <h2>Social Icon</h2>
        <ul class="list--social">
          <li>
            <a href="#">
              <svg class="social--icon">
                <use
                  xlink:href="../../assets/sprite.svg#icon-facebook-official"
                ></use>
              </svg>
              <p>Facebook</p>
            </a>
          </li>
          <li>
            <a href="#">
              <svg class="social--icon">
                <use xlink:href="../../assets/sprite.svg#icon-twitter"></use>
              </svg>
              <p>Twitter</p>
            </a>
          </li>
          <li>
            <a href="#">
              <svg class="social--icon">
                <use xlink:href="../../assets/sprite.svg#icon-behance"></use>
              </svg>
              <p>Behance</p>
            </a>
          </li>
          <li>
            <a href="#">
              <svg class="social--icon">
                <use xlink:href="../../assets/sprite.svg#icon-linkedin"></use>
              </svg>
              <p>Linkedin</p>
            </a>
          </li>
          <li>
            <a href="#">
              <svg class="social--icon">
                <use xlink:href="../../assets/sprite.svg#icon-instagram"></use>
              </svg>
              <p>Instagram</p>
            </a>
          </li>
        </ul>
      </div>
      <div class="footer__item">
        <h2>Subscribe</h2>
        <p>
          Let me know more when you publick some intresting: news, ideas,
          updates and latest features
        </p>
        <input type="text" placeholder="Email Address" />
      </div>
    </div>
    <div class="footer--rights">
      <h3>© 2021. All rights reserved.</h3>
      <ul class="rights--icons">
        <li>
          <a href="#"
            ><svg class="social--icon">
              <use
                xlink:href="../../assets/sprite.svg#icon-facebook-official"
              ></use></svg
          ></a>
        </li>
        <li>
          <a href="#"
            ><svg class="social--icon">
              <use xlink:href="../../assets/sprite.svg#icon-twitter"></use></svg
          ></a>
        </li>
        <li>
          <a href="#"
            ><svg class="social--icon">
              <use
                xlink:href="../../assets/sprite.svg#icon-google-plus"
              ></use></svg
          ></a>
        </li>
      </ul>
    </div>
  </footer>
</template>

<style lang="scss" scoped>
.footer {
  width: 100%;
  background-color: #333333;
  padding: 3rem 4rem;
  padding-bottom: 0rem;
  color: white;

  @media only screen and (max-width: 720px) {
    padding: 3rem 1rem;
  }

  &--items {
    display: grid;
    grid-template-columns: repeat(4, 1fr);

    @media only screen and (max-width: 1140px) {
      grid-template-columns: repeat(2, 1fr);
      grid-row-gap: 1rem;
    }

    @media only screen and (max-width: 720px) {
      grid-template-columns: repeat(1, 1fr);
      grid-row-gap: 1rem;
    }
  }

  &__item {
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;

    @media only screen and (max-width: 720px) {
      align-items: flex-start;
    }
  }

  h2 {
    font-size: 1.7rem;
    font-weight: 900;
    margin-bottom: 2rem;
  }

  p {
    font-size: 1.1rem;
    font-weight: 300;
  }

  .list--repairs {
    list-style: circle;

    li {
      margin-bottom: 0.5rem;

      &:hover {
        a {
          font-weight: 500;
        }
      }

      a {
        text-decoration: none;
        color: white;
        font-weight: 300;
      }
    }
  }

  .list--social {
    list-style: none;

    li {
      margin-bottom: 0.5rem;

      &:hover {
        .social--icon {
          fill: white;
          width: 1.3rem;
          height: 1.3rem;
        }
      }

      a {
        display: flex;
        align-items: center;
        color: white;
        text-decoration: none;
      }
    }
  }

  input {
    margin-top: 1.5rem;
    height: 2rem;
    padding: 1rem;
    font-size: 1rem;
  }
}

.footer--rights {
  border-top: 1px solid rgb(70, 70, 70);
  width: 100%;
  padding: 1rem;
  margin-top: 2rem;
  display: flex;
  justify-content: space-between;

  h3 {
    font-weight: 500;
    font-size: 1rem;
  }

  ul {
    display: flex;
    list-style: none;
  }
}

.social--icon {
  width: 1.2rem;
  height: 1.2rem;
  fill: rgb(189, 189, 189);
  margin-right: 1rem;
}
</style>