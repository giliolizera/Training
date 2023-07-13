<template>
    <div class="bg-blue-300">
        <div class="w-full px-4 pt-16">
            <div class="mx-auto w-full max-w-md rounded-2xl bg-blue-400 p-2">
                <div class="grid grid-flow-col justify-stretch space-x-1">
                    <button class="rounded-lg bg-blue-400 px-4 py-2 text-center text-sm text-white font-medium hover: hover:text-blue-700 hover:bg-blue-300 focus:outline-none">Recent</button>

                    <button class="rounded-lg bg-blue-400 px-4 py-2 text-center text-sm  text-white font-medium hover: hover:text-blue-700 hover:bg-blue-300 focus:outline-none">Popular</button>

                    <button class="rounded-lg bg-blue-400 px-4 py-2 text-center text-sm  text-white font-medium hover:text-blue-700 hover:bg-blue-300 focus:outline-none">Trending</button>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data: () => ({
        Recent: [
            {
            id: 1,
            title: 'Does drinking coffee make you smarter?',
            date: '5h ago',
            commentCount: 5,
            shareCount: 2,
            },
            {
            id: 2,
            title: "So you've bought coffee... now what?",
            date: '2h ago',
            commentCount: 3,
            shareCount: 2,
            },
        ],
        Popular: [
            {
            id: 1,
            title: 'Is tech making coffee better or worse?',
            date: 'Jan 7',
            commentCount: 29,
            shareCount: 16,
            },
            {
            id: 2,
            title: 'The most innovative things happening in coffee',
            date: 'Mar 19',
            commentCount: 24,
            shareCount: 12,
            },
        ],
        Trending: [
            {
            id: 1,
            title: 'Ask Me Anything: 10 answers to your questions about coffee',
            date: '2d ago',
            commentCount: 9,
            shareCount: 5,
            },
            {
            id: 2,
            title: "The worst advice we've ever heard about coffee",
            date: '4d ago',
            commentCount: 1,
            shareCount: 2,
            },
        ],
    }),
}
</script>