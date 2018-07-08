# Unity-RichText
**Rich Text**

>![RichTextStyle](https://github.com/ChallengerCY/Unity-RichText/blob/master/Unity-RichText/Picture%26gif/RichTextStyle.png)
>
>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UI元素的文本和text meshes可以合并多种字体风格和大小。Rich Text同时支持UI系统和老版本的GUI系统。Text, GUIStyle, GUIText 还有 TextMesh classes 拥有Rich Text设置，可以指示Unity寻找文本中的富文本标签。Debug.Log可以使用富文本标记来增强日志的输出信息。标签不会显示出来而是直接控制对应文本的显示。

**Markup format**

>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Markup system受HTML语言的启发，但并不打算与标准的HTML完全兼容。基本的设计思路是，文本的一部分可以包含在一对匹配的标记中。
>
> ![Demo1](https://github.com/ChallengerCY/Unity-RichText/blob/master/Unity-RichText/Picture%26gif/Demo1.png)
> 
>"We are <b>not</b> amused"
>
>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;标签是携带尖括号的文字。标签内的文本是这个标签的名字。末尾的标记相对于开始的标记多了一个/。标记不会直接显示给用户，而是被解释为对它们所封装的文本进行样式化的说明。例子中的b标签代表了对not使用粗体样式
>
>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;通过嵌套的方式可以对一个文本添加多种样式
>
>![Demo2](https://github.com/ChallengerCY/Unity-RichText/blob/master/Unity-RichText/Picture%26gif/Demo2.png)
>
>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;i标签代表采用斜体。所以文本会在屏幕中显示We are
><b><i>definitely not</i></b> amused。
>
>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;下面的例子中你会看到标签开始的顺序和结束的顺序不一样。这样做的原因是多种标签嵌套不一定要控制同一段文本。
>
>![Demo3](https://github.com/ChallengerCY/Unity-RichText/blob/master/Unity-RichText/Picture%26gif/Demo3.png)
>
>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;可以得到 We are <b>absolutely <i>definitely</i> not</b> amused

**Tag parameters**
>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;一些标签会对文本产生全有或全无的效果，也有一些标签需要设置属性来改变文本。例如，color标签需要知道应用哪种颜色。这时候就需要设置color标签的属性。
>
>![DEMO4](https://github.com/ChallengerCY/Unity-RichText/blob/master/Unity-RichText/Picture%26gif/DEMO4.png)
>
>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;注意结尾标签并没有包含属性。属性可以使用括号包围起来，但并不是特别需要。
>
>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;这里可以查看官网列举出来的所有标签[https://docs.unity3d.com/Manual/StyledText.html](https://docs.unity3d.com/Manual/StyledText.html)

**Editor GUI**
>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;在编辑器GUI系统中默认禁用富文本，但是可以使用自定义GUI样式显式地启用富文本将richText属性设置为true，并将样式传递给相关的GUI函数。
