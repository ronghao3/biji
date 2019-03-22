## 3月22日,天气:阴转晴
## js笔记我透
> 数组

+ new array();
+ var arr=[1,6,8,6,7,9,"吃了吗"];这些是数组.
+ length 数组长度
+ concat();这是链接数组
+  将一个数组与另一个或多个数组或非数组元素合并 并返回合并后的数组
```
			var arr = [1,2,3,4];
			var arr1 = [true,false,"split"];
			// arr = arr.concat(arr1);
			arr = arr.concat(1,2,["a","b","c"]);
			console.log(arr);
```			
+ 结果[1, 2, 3, 4, 1, 2, "a", "b", "c"]


+ 数组各个元素是通过指定的分隔符进行连接成为一个字符串，并返回字符串。语法： 
```
			arrayObject.join(separator)
			var arr = [1,2,3,4,5];
			arr = arr.join(" * ");
			console.log(arr);
```
+ 结果 [1 * 2 * 3 * 4 * 5]


```
			// split() 将字符串转换成数组并返回数组。语法：
			// stringObject.split(separator,howmany)
			var str = "smith,john,gina,white,kate";
			// var arr = str.split();	// ["smith,john,gina,white,kate"]
			// var arr = str.split(",");	// ["smith", "john", "gina", "white", "kate"]
			// var arr = str.split("h");		//	["smit", ",jo", "n,gina,w", "ite,kate"]
			var arr = str.split(",", 3);		//	 ["smith", "john", "gina"]
			console.log(arr);
			//两个参数,第一个是转换为数组,第二个是数组的长度为几
```

+ 数组的增删

```
		//unshift() push() 从数组前，后插入一个或多个元素，并返回数组的长度,更改变化反应在原数组上
					var arr = [1,2,3];
					//var length = arr.unshift("front");这个是往数组最前面加,加的元素变成第一个
					//length = arr.push("behand",true,12);这个是往后面加
		 			//console.log(length);
					//console.log(arr);
					
					 // shift() pop() 删除数组第一/倒一的元素，并返回被删除的元素
					 console.log(arr);
```

+冒泡排序

```
var temp;//用来当容器(第三方)
		var arr=[1,19,9,2,7,17];
// 		for (var i=0;i<arr.length-1;i++) {//这个循环减去数组最后的一个数
// 			if(arr[i]>arr[i+1]){		//这是对比循环过后的i和i+1(第一位和第二位)
// 				temp = arr[i+1]; 		//这是对比循环过后的i和i+1(第一位和第二位)
// 				arr[i+1] = arr[i];		//这是对比循环过后的i和i+1(第一位和第二位)
// 				arr[i] = temp;			//把小的那一位赋值给大的那一位之前的容器里
// 			}							//换位置
// 			console.log(arr);
// 		}
// 		console.log(arr);
		for(var i=0; i<arr.length-1; i++){		//这个循环减去数组最后的一个数	 也就是[1,19,9,2,7]
			for (var j=i+1; j<arr.length; j++) {//这个循环减去数组最前面的一个数 [19,9,2,7,17]
				if(arr[i]>arr[j]){				//这是对比循环过后的i和i+1(第一位和第二位)
					temp=arr[j];				//这是对比循环过后的i和i+1(第一位和第二位)
					arr[j]=arr[i];				//这是对比循环过后的i和i+1(第一位和第二位)
					arr[i]=temp;				//把小的那一位赋值给大的那一位之前的容器里
				}								//换位置
			}
			 console.log(arr);
		}console.log(arr);
		
```