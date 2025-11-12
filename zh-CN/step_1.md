`IntersectionObserver` 用于检测元素（例如 `<img>`，`<p>` 或 `<div>`）何时进入或离开用户的浏览器视口。

它通常用于“懒加载”图像和触发动画。

观察器主要有三个部分：

**目标元素**：你指定希望观察器观察的元素。 这些是你所感兴趣的元素，你想知道他们是否已经进入或者退出视口。

\*\*回调：\*\*回调是当观察元素进入或退出视口时触发的函数。 例如，该函数可以向控制台输出消息，或者更改 HTML 元素。

\*\*选项：\*\*你还可以向交叉观察器提供一些选项，例如设置阈值。 阈值是需要可见才能触发回调的观察元素的数量。 例如，你可以使用阈值 0.5 在元素可见度为 50% 时发出通知，或者使用阈值 1 在元素完全可见时发出通知。

以下是 [更多 Web](https://projects.raspberrypi.org/en/raspberrypi/more-web) 路径中的 [动画故事](https://projects.raspberrypi.org/en/projects/animated-story) 项目使用 `IntersectionObserver` 的示例：

## --- code ---

language: js
filename:
line_numbers: true
line_number_start: 1
line_highlights:
-----------------------------------------------------

const bounceObserver = new IntersectionObserver((entries) => {
if (entries[0].isIntersecting) {
console.log("视口中的弹跳触发器");
}
});
bounceObserver.observe(document.querySelector("#hideBounce"));

\--- /code ---

在第 1 行中，`entries` 是网页上所有具有 `id="hideBounce"` 属性的元素的集合。 这些是目标元素，如第 6 行的观察器调用中所指定。

项目的集合称为“数组”。

设置 `bounceObserver` 来观察 `entries` 数组中的第一个（在本例中是唯一的）项目何时进入视口（使用第 2 行的 `isIntersecting`）。

当它发生时，观察器“回调”向控制台输出一条消息（第 3 行）。
