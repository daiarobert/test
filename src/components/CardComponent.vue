<template>
  <div class="hello">
    <!-- Card container -->
    <div class="card">
      <!-- Back button wrapper -->
      <div class="back-card-wrapper">
        <a href="#" class="back-wrapper"
          ><img class="arrow-back" src="../assets/Arrow.svg" />

          <p class="back-text">Back</p>
        </a>
      </div>
      <!-- Card image -->
      <img alt="bg-image" class="bg-image" :src="cardInfo.headerImage" />
      <div class="card-info-wrapper">
        <div class="card-info-container">
          <!-- Card title and follow section -->
          <div class="card-title-wrapper">
            <div class="card-title f900">
              <div>{{ cardInfo.name }}</div>
              <div class="follow-section">
                <img src="../assets/follow_icon.svg" />
                <div class="follow-text">FOLLOW</div>
              </div>
            </div>
            <img class="more-icon" src="../assets/More_icon.svg" />
          </div>
          <div class="stats-wrapper">
            <div class="stats-container">
              <!-- Loop through stats -->
              <div
                v-for="(stat, index) in cardInfo.stats"
                :key="index"
                class="stats"
              >
                <div class="stats-value f900">{{ stat.value }}</div>
                <div class="stats-label f900">{{ stat.label }}</div>
              </div>
            </div>
          </div>
          <!-- Categories section -->
          <div class="categories f900">CATEGORIES</div>
          <!-- Categories list -->
          <ul>
            <li
              v-for="(category, index) in cardInfo.categories"
              :key="index"
              class="border-li"
            >
              <div class="content-container">
                <div class="content-title">{{ category }}</div>
                <img class="arrow-right-icon" src="../assets/Arrow_right.svg" />
              </div>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },

  data() {
    return {
      cardInfo: {
        headerImage: require("../assets/Header_image/Header_image.png"),
        name: "Steve Jobs",
        stats: [
          { label: "PATENTS", value: 313 },
          { label: "FOLLOWERS", value: "1M 50K" },
          { label: "FOLLOWING", value: 361 },
        ],
        categories: ["Electronic Devices", "Design", "Transportation"],
      },
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
.card {
  display: flex;
  flex-direction: column;
  border-radius: 35px;
  max-width: 375px;
  color: #462681;

  .back-wrapper {
    position: absolute;
    display: flex;
    justify-content: center;
    align-items: center;
    text-decoration: none;
    margin-top: 15.44px;

    .arrow-back {
      display: flex;
      margin-left: 15px;
    }

    .back-text {
      font-weight: 400;
      margin-left: 10px;
      font-size: 18px;
      color: white;
    }
  }

  .card-info-wrapper {
    border-radius: 35px;
    background-color: #fff;
    margin-top: -52px;
    position: relative;
    z-index: 100;
    color: #462681;

    .card-info-container {
      padding-left: 25px;
      padding-top: 20px;
      padding-right: 25px;

      .card-title-wrapper {
        display: flex;

        .card-title {
          font-size: 44px;
          max-height: 75px;

          .follow-section {
            display: flex;
            justify-content: flex-start;
            align-items: center;

            .follow-text {
              font-size: 14px;
              margin-left: 5px;
            }
          }
        }

        .more-icon {
          margin-left: auto;
          margin-bottom: 39px;
          margin-top: 30px;
        }
      }
    }
  }

  .stats-wrapper {
    border-top: #462681 1px solid;
    border-bottom: #462681 1px solid;
    margin: 0px;
    margin-top: 20px;

    .stats-container {
      display: flex;
      justify-content: space-evenly;
      align-items: center;
      max-height: 62px;

      .stats-value {
        font-size: 24px;
        margin-top: 6px;
      }
      .stats-label {
        font-size: 14px;
        margin-bottom: 11px;
      }
    }
  }

  .categories {
    display: flex;
    font-size: 14px;
    margin-top: 20px;
    margin-bottom: 30px;
  }

  .content-container {
    display: flex;
    justify-content: center;
    align-items: center;

    .content-title {
      font-size: 25px;
      font-weight: 400;
      margin-bottom: 20px;
    }
    .arrow-right-icon {
      margin-left: auto;
      margin-bottom: 20px;
    }
  }

  ul {
    list-style-type: none;
    padding: 0;
    margin: 0;
    display: flex;
    flex-direction: column;

    .border-li {
      border-bottom: #462681 1px solid;
      margin: 0px;
      margin-bottom: 20px;
    }
    .border-li:last-child {
      margin-bottom: 6px;
    }
  }
}

.bg-image {
  position: relative;
  z-index: -10;
}

.f900 {
  font-weight: 900;
}

@media screen and (min-width: 376px) {
  .card {
    max-width: 650px;
    margin-left: auto;
    margin-right: auto;
  }
}
</style>
