# SearchSpinner2
不清楚怎么回事,创建一个module,然后通过app关联,总是报奇怪的错误,所以只能集成在app目录里面<br/>
效果图:<br/>
<img src="https://github.com/nanjolnoSat/SearchSpinner2/blob/master/pic1.gif"/><img src="https://github.com/nanjolnoSat/SearchSpinner2/blob/master/pic2.gif"/><br/>
使用方式:<br/>
1,可以继承SearchSpinner<T>,然后给个泛型,这样在findViewById的时候就不用强转,并给<b>filterMode</b>这个变量赋值,这个是负责当输入框有内容的时候,根据输入框的内容设置是否显示遍历到的内容.<b>contentMode</b>可以不赋值,如果空的话直接调用该对象分的toString()方法.<br/>
2,也可以直接使用StringSearchSpinner,<b>filterMode</b>默认是判断输入遍历到的字符串是否包含输入的内容.<br/>
3,BaseSpinnerAdapter需要重写2个方法,一个是<b>getNormalView</b>,这个方法的用法和ListView的getView是一样的,然后是<b>getSearchView</b>.这个是当输入框有内容的时候调用,如果输入框有内容和没有内容的显示方式是一样的话,就直接调用getNormalView方法就行了.在<a href="https://github.com/nanjolnoSat/SearchSpinner2/blob/master/app/src/main/java/com/mishaki/searchspinner2/adapter/StringSpinnerAdapter.kt">StringSpinnerAdapter</a>和<a href="https://github.com/nanjolnoSat/SearchSpinner2/blob/master/app/src/main/java/com/mishaki/searchspinner2/adapter/StringMarkSpinnerAdapter.kt">StringMarkSpinnerAdapter</a>给出了2种不同的用法.
<h3>SearchSpinner自带的属性</h3>
<table>
<tr>
<th>属性名称</th>
<th>类型</th>
<th>注释</th>
</tr>
<tr align="center">
<td>ss_elevationSize</td>
<td>dimension</td>
<td>阴影的大小</td>
</tr>
<tr align="center">
<td>ss_adapterItemHeight</td>
<td>dimension</td>
<td>adapter的高度</td>
</tr>
<tr align="center">
<td>ss_defaultText</td>
<td>string</td>
<td>默认的文本</td>
</tr>
<tr align="center">
<td>ss_textColor</td>
<td>color</td>
<td>默认/选择后显示的文本的颜色</td>
</tr>
<tr align="center">
<td>ss_textSize</td>
<td>dimension</td>
<td>默认/选择后文本的大小</td>
</td>
<tr align="center">
<td>ss_showArrow</td>
<td>boolean</td>
<td>是否显示三角形</td>
</tr>
<tr align="center">
<td>ss_changeArrowColor</td>
<td>boolean</>
<td>是否改变三角形的颜色,<b>默认不改变</b></td>
</tr>
<tr align="center">
<td>ss_arrowColor</td>
<td>color</>
<td>如果改变的话改变的颜色,默认<b>#FFAAAAAA</b></td>
</tr>
<tr align="center">
<td>ss_arrowImage</td>
<td>color|reference</td>
<td>三角形的图片,<b>要更换</b>的时候才使用</td>
</tr>
<tr align="center">
<td>ss_arrowWidth</td>
<td>dimension</>
<td>三角形的宽度,不设置使用<b>原始高度</b></td>
</tr>
<tr align="center">
<td>ss_arrowHeight</td>
<td>dimension</td>
<td>三角形的高度,不设置使用<b>原始高度</b></td>
</tr>
<tr align="center">
<td>ss_tipText</td>
<td>string</td>
<td>当没有搜索结果的时候,提示的文本,默认<b>暂无搜索结果</b></td>
</tr>
<tr align="center">
<td>ss_tipTextColor</td>
<td>color</td>
<td>当没有搜索结果的时候,提示的文本的<b>颜色</b>,默认<b>@android:color/black</b></td>
</tr>
<tr align="center">
<td>ss_tipTextSize</td>
<td>dimension</td>
<td>当没有搜索结果的时候,提示的文本的<b>大小</b>,默认<b>15sp</b></td>
</tr>
<tr align="center">
<td>ss_tipViewHeight</td>
<td>dimension</td>
<td>当没有搜索结果的时候,提示的文本的<b>高度</b>,默认跟随根View的高度</td>
</tr>
<tr align="center">
<td>ss_searchTextSize</td>
<td>dimension</td>
<td>搜索框的文本的<b>大小</b>,默认<b><15sp/b></td>
</tr>
<tr align="center">
<td>ss_searchTextColor</td>
<td>color</td>
<td>搜索框的文本的<b>颜色</b>,默认<b>#FF000000</b></td>
</tr>
<tr align="center">
<td>ss_searchHint</td>
<td>string</td>
<td>搜索框<b>提示的文本</b>,默认空</td>
</tr>
<tr align="center">
<td>ss_searchHintColor</rd>
<td>color</td>
<td>搜索框<b>提示的文本的颜色</b>,默认<b>#FFFAFAFA</b></td>
</tr>
<tr align="center">
<td>ss_searchHeight</td>
<td>dimension</td>
<td>搜索框的<b>高度</b>,默认跟随根View的高度</td>
</tr>
</table>
<h3>StringSearchSpinner附带的属性</h3>
<table>
<tr>
<th>属性名称</th>
<th>类型</th>
<th>注释</th>
</tr>
<tr align="center">
<td>ss_ignoreCase</td>
<td>boolean</td>
<td>搜索的时候是否忽略大小写</td>
</tr>
</table>
