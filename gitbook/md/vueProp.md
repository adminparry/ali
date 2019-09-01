# 在 Vue 中子组件为何不可以修改父组件传递的 Prop

做过vue开发的同学应该都遇到过这样的报错
Avoid mutating a prop directly since the value will be " +
            "overwritten whenever the parent component re-renders. " +
            "Instead, use a data or computed property based on the prop's " +
            "value. Prop being mutated

然后排查错误也明显能找到单向数据流的概念 也可以通过官方网站找到作者给的建议基于prop的data或者computed来做也可以触发一个action来做


