#### You can make the text in the status of your discord bot change according to the second you specify.

```js
client.on('ready', async () => {
    let activityes = [
        { text: "♾️ CihatKsm", waitSecond: 5 },
        { text: "drizzlydeveloper.xyz", waitSecond: 5 },
        { text: "video.drizzlydeveloper.xyz", waitSecond: 5 },
        { text: "radio.drizzlydeveloper.xyz", waitSecond: 5 }
    ]

    await setActivity(activityes, 0)

    async function setActivity(activityes, number) {
        if (!activityes[number]) return setActivity(activityes, 0)
        let text = activityes[number].text
        client.user.setActivity(text)
        setTimeout(() => setActivity(activityes, number + 1), Number(activityes[number].waitSecond * 1000))
    }
})
