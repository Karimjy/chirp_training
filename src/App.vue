<template>
  <header class="px-5 py-10 md:px-10">
    <NavigationComponent @scrollTo=scrollMeTo />

    <div class="lg:flex lg:flex-row-reverse lg:items-center lg:justify-between">
      <div class="intro my-10 lg:max-w-lg">
        <img src="@/assets/HeroImageDesk.png" class="md:hidden lg:inline" />
        <img
          src="@/assets/HeroImageTablet.png"
          class="hidden md:inline lg:hidden"
        />
      </div>

      <div class="el lg:w-1/2">
        <h1 class="font-bold text-black leading-tight">
          Twitter analytics taken to a whole new level.
        </h1>
        <p class="my-5">
          Chirp is a suite of Twitter analytics that will help you better
          understand your audience, which tweets they like, and most
          importantly, when they are the most active on Twitter
        </p>

        <div class="btns flex flex-col items-center mb-7 md:flex-row">
          <TwitterButtonComponent />
          <p class="more font-bold mt-6 md:mt-0 md:ml-6">Learn more &#10132;</p>
        </div>

        <div class="users">
          <div class="list flex">
            <img src="@/assets/userAvatar09.svg" alt="" />
            <img src="@/assets/userAvatar08.svg" alt="" />
            <img src="@/assets/userAvatar07.svg" alt="" />
            <img src="@/assets/userAvatar06.svg" alt="" />
            <img src="@/assets/userAvatar05.svg" alt="" />
            <img src="@/assets/userAvatar04.svg" alt="" />
            <img src="@/assets/userAvatar03.svg" alt="" />
            <img src="@/assets/userAvatar02.svg" alt="" />
            <img src="@/assets/userAvatar01.svg" alt="" />
          </div>
          <p class="mt-5 md:w-4/6">
            Join <span>195</span> others who have analyzed their followers and
            scheduled <span>1342</span> tweets!
          </p>
        </div>
      </div>
    </div>
  </header>

  <main>
    <div class="features px-5 py-20 md:px-10 lg:px-0">
      <h1 class="font-bold text-black leading-tight md:w-3/4">
        Features that help you Tweet&nbsp;smarter.
      </h1>

      <div class="listFeatures mt-9 lg:grid lg:grid-cols-2 lg:gap-10">
        <div
          v-for="feature in listFeatures"
          :key="feature.title"
          class="featureBloc mb-6 lg:mb-0 lg:h-full"
        >
          <FeatureComponent
            :image="feature.img"
            :title="feature.title"
            :desc="feature.desc"
          />
        </div>
      </div>
    </div>

    <div class="customer px-5 py-16 md:px-0">
      <h1 class="font-bold text-black leading-tight md:pl-10">
        What our customers say
      </h1>

      <div
        class="
          listTweets
          mt-9
          md:flex md:flex-nowrap md:gap-4 md:overflow-x-auto md:px-10 lg:px-0 lg:overflow-visible
        "
      >
        <div
          v-for="tweet in listTweets"
          :key="tweet.title"
          class="tweetBloc mb-6 md:mb-0 md:flex-none"
        >
          <TweetComponent
            :profile="tweet.profile"
            :name="tweet.name"
            :tag="tweet.tag"
            :desc="tweet.desc"
            :like="tweet.like"
            :date="tweet.date"
          />
        </div>
      </div>
    </div>

    <div class="prices px-5 py-16 md:px-10">
      <div class="head px-5">
        <h1 class="font-bold text-black leading-tight text-center">
          One simple price plan.
        </h1>
        <p class="text-center mt-4 pb-14">
          Start growing your Twitter account by analyzing your follower's
          patterns.
        </p>
      </div>

      <div ref="pricing" class="plan rounded py-11 md:px-14">
        <div class="descriptif px-14 md:px-0">
          <div class="type">
            <p>Monthly</p>
            <div class="price font-bold text-black">
              $9<span class="font-normal">/mo</span>
            </div>
          </div>

          <ul>
            <li>
              <img src="@/assets/Checkmark.svg" alt="" />
              <p>Unlimited* scheduled tweets and threads.</p>
            </li>
            <li>
              <img src="@/assets/Checkmark.svg" alt="" />
              <p>Schedule up to 3 weeks in advance.</p>
            </li>
            <li>
              <img src="@/assets/Checkmark.svg" alt="" />
              <p>Real-time audience analytics tracking up to 5k followers.</p>
            </li>
          </ul>
        </div>
        <div class="cta">
          <TwitterButtonComponent :fullwidth=true />
        </div>
      </div>
    </div>
  </main>

  <FooterComponent class="px-5 md:px-10" />
</template>

<script setup>
import { ref } from 'vue'
import NavigationComponent from "@/components/NavigationComponent.vue";
import TwitterButtonComponent from "@/components/TwitterButtonComponent.vue";
import FeatureComponent from "@/components/FeatureComponent.vue";
import TweetComponent from "@/components/TweetComponent.vue";
import FooterComponent from "@/components/FooterComponent.vue";

const listFeatures = [
  {
    img: "IconPlot.png",
    title: "Analytics",
    desc: "We constantly monitor your audience as it grows - so you can Tweet when your folllowers are most likely to be online and ready to engage with your content.",
  },
  {
    img: "IconSmiley.png",
    title: "Smart Analyzer",
    desc: "Chirp automatically recognizes your followers' most active tomes and automatically send you notifications if you're missing out on an opportunity.",
  },
  {
    img: "IconMoney.png",
    title: "Scheduled Your Tweets",
    desc: "Quality tweets drive tons of engagement. With Chirp, you can write tweets in an advance and schedule them when your audience is mosr likely to read.",
  },
  {
    img: "IconSun.png",
    title: "Dark Mode",
    desc: "Friendly on the eyes, no atter what time you write your Tweets. All colors are chosen to make sure your eyes are at ease at all times.",
  },
];

const listTweets = [
  {
    profile: "userAvatar01.svg",
    name: "Sara May",
    tag: "@sara_may",
    desc: "I just tried out @chirp and it's amazing, love all the analytics I can see.",
    like: "2",
    date: "March 2, 2021",
  },
  {
    profile: "userAvatar02.svg",
    name: "Jack Scott",
    tag: "@jackscott_",
    desc: "I initially started using Chirp to support the co-founder as I personally knew him, bu after having tried it out a few weeks, I can genuinely say this changed my Twitter game.",
    like: "32",
    date: "March 2, 2021",
  },
  {
    profile: "userAvatar03.svg",
    name: "Jessica May",
    tag: "@jmay98",
    desc: "Absolutely love everything about Chirp, from the design to how everything works smoothly",
    like: "221",
    date: "March 2, 2021",
  },
];

const pricing = ref()

function scrollMeTo() {
    var element = pricing.value;
    var top = element.offsetTop;

    window.scrollTo({top: top, behavior: 'smooth'});
  }
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Inter:wght@400;500;700&display=swap");

#app {
  font-family: "Inter", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #000000;
  font-weight: 400;

  h1 {
    font-size: 34px;
  }

  header {
    background-color: #fbf8f3;
    color: #737373;
    font-size: 18px;

    .btns {
      .more {
        color: #1f7898;
      }
    }

    .users {
      .list > img {
        margin-right: -22px;
      }

      p {
        & span {
          color: #1f7898;
          font-weight: bold;
        }
      }
    }
  }

  .tweetBloc:last-child,
  .featureBloc:last-child {
    margin-bottom: 0;
  }

  .customer {
    background-color: #d7f5f5;
  }

  .prices {
    color: #737373;

    .plan {
      background-color: #fbf8f3;
      border: 1px solid #ffad23;

      .type {
        font-size: 22px;
        padding-bottom: 13px;
        border-bottom: 1px solid #cecece;

        .price {
          font-size: 52px;
          span {
            font-size: 22px;
          }
        }
      }

      ul {
        margin-top: 23px;
        padding-bottom: 13px;
        border-bottom: 1px solid #cecece;

        li {
          display: flex;
          align-items: start;
          margin-bottom: 1em;

          p {
            margin-left: 1.1em;
          }
        }
      }

      .cta {
        width: 90%;
        margin: 0 auto;
        margin-top: 23px;
      }
    }
  }
}

@media (min-width: 768px) {
  #app {
    .el h1 {
      font-size: 54px;
      line-height: 1.2;
    }

    .tweetBloc {
      width: 365px;
    }

    .prices .plan,
    .prices .head {
      max-width: 530px;
      margin: 0 auto;
    }

    .prices .plan .cta {
      width: 100%;
    }
  }
}

@media (min-width: 1024px) { 
  header > div, main > div, footer > div{
    max-width: 1132px;
    margin: 0 auto;
  }

    .customer{
    max-width: none;

    & > * {
    max-width: 1132px;
    margin: 0 auto;

    }
  }
 }
</style>
