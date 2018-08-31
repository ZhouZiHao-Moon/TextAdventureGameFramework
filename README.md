# 文字冒险游戏框架

# TextAdventureGameFramework

## 介绍

使用JavaScript（包括jQuery）编写的轻便的文字冒险游戏框架，会越来越完善

## 框架结构

	index.html
	static/
		txt/ 保存文字内容
		pic/ 保存图片
		js/ JavaScript代码
		mycss.css 样式表

## 文字内容编辑

	{
		"content":[
			"content1",
			"content2",
			"content3"
		], //该事件的文字描述
		"next":[ //选项，为数组，可多个添加
			{
				"order":"", //这个选项的描述
				"number":"" //这个选项通向的下一个事件编号
			},
			{
				"order":"",
				"number":""
			}
		],
		"end":"0", //整数，为0表示未结束，为其他数字表示为结局的编号，会显示static/pic/下的相应图片
		"timeout":"1000" //设置延时
	}

## 延时显示功能

在文字内容文件中新增了timeout选项，该选项会使content中的内容每隔一段时间依次显示（毫秒）。实际运行为：立即显示content1，隔timeout毫秒后显示content2，……，直到最后一个content之后再隔timeout毫秒显示下一步的选项或是结局。

## 注意事项

1. 需要将整个项目传到服务器环境下运行
2. 虽然文字内容的格式是txt，但它其中的内容为json
3. 如果需要特殊判定（比如角色之前有没有触发哪个剧情），可以在JavaScript的step()函数中添加条件判断语句

## 更新内容

2018-8-31：更新延时显示功能