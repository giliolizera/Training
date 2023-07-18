<template>
  <div class="bg-blue-300">
    <div class="w-full px-4 pt-16">
      <div class="mx-auto w-full max-w-md rounded-2xl bg-blue-400 p-2">
        <div class="grid grid-flow-col justify-stretch space-x-1">
          <button v-for="(tab,index) in tabs" :key="index" @click="active = tab.id"
            type="button"
            :class="['rounded-lg px-4 py-2 text-center text-sm text-white font-medium hover: hover:text-blue-700 hover:bg-blue-300 focus:outline-none', active === tab.id ? 'bg-blue-500' : 'bg-blue-400']"
          >
            {{ tab.descricao }}
          </button>
        </div>
      </div>
    </div>
    <div class="bg-blue-300 w-full pt-2">
      <div class="mx-auto w-full max-w-md rounded-2xl bg-white px-5 relative hover:bg-gray-100">
          <div v-if="active === 1">
            <div v-for="(recent,index) in Recent" :key="index">
              <div class="pt-5">
                <h3 class="mt-1 text-sm font-medium leading-5">{{ recent.title }}</h3>
                <ul class="mt-1 flex space-x-1 text-xs font-normal leading-4 text-gray-500">
                  <li>{{ recent.date }}</li>
                  <li>{{ recent.commentCount }} comments</li>
                  <li>{{ recent.shareCount }} shares</li>
                </ul>
              </div>
            </div>
            <div class="py-4"></div>
          </div>
          <div v-if="active === 2">
            <div v-for="(popular,index) in Popular" :key="index">
              <div class="pt-5">
                <h3 class="mt-1 text-sm font-medium leading-5">{{ popular.title }}</h3>
                <ul class="mt-1 flex space-x-1 text-xs font-normal leading-4 text-gray-500">
                  <li>{{ popular.date }}</li>
                  <li>{{ popular.commentCount }} comments</li>
                  <li>{{ popular.shareCount }} shares</li>
                </ul>
              </div>
            </div>
            <div class="py-4"></div>
          </div>
          <div v-if="active === 3">
            <div v-for="(trending, index) in Trending" :key="index">
              <div class="pt-5">
                <h3 class="mt-1 text-sm font-medium leading-5">{{ trending.title }}</h3>
                <ul class="mt-1 flex space-x-1 text-xs font-normal leading-4 text-gray-500">
                  <li>{{ trending.date }}</li>
                  <li>{{ trending.commentCount }} comments</li>
                  <li>{{ trending.shareCount }} shares</li>
                </ul>
              </div>
            </div>
            <div class="py-4"></div>
          </div>
      </div>
    </div>
  </div>
  <div class="bg-blue-300 w-full h-28"></div>
</template>

<script>

export default{
    data(){
        return {
            tabs: [
                {
                    id: 1,
                    descricao: 'Recent'
                },
                {
                    id: 2,
                    descricao: 'Popular'
                },
                {
                    id: 3,
                    descricao: 'Trending'
                }
            ],
            Recent: [
              {
                id: 1,
                title: "Does drinking coffee make you smarter?",
                date: "5h ago",
                commentCount: 5,
                shareCount: 2,
              },
              {
                id: 2,
                title: "So you've bought coffee... now what?",
                date: "2h ago",
                commentCount: 3,
                shareCount: 2,
              },
            ],
            Popular: [
              {
                id: 1,
                title: "Is tech making coffee better or worse?",
                date: "Jan 7",
                commentCount: 29,
                shareCount: 16,
              },
              {
                id: 2,
                title: "The most innovative things happening in coffee",
                date: "Mar 19",
                commentCount: 24,
                shareCount: 12,
              },
            ],
            Trending: [
              {
                id: 1,
                title: "Ask Me Anything: 10 answers to your questions about coffee",
                date: "2d ago",
                commentCount: 9,
                shareCount: 5,
              },
              {
                id: 2,
                title: "The worst advice we've ever heard about coffee",
                date: "4d ago",
                commentCount: 1,
                shareCount: 2,
              },
            ],
            active: 1
          }
      }
  }
</script>