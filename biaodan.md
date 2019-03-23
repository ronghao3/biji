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

+选择排序

```
// 选择排序（Selection sort）是一种简单直观的排序算法。它的工作原理是每一次从待排序的数据元素中选出最小（或最大）的一个元素，存放在序列的起始位置，直到全部待排序的数据元素排完。
			var arr = [4,38,3,5,8,2,1];
			var minIndex,temp;
			document.write(arr);
			
			for(var i = 1; i < arr.length; i ++){//6
				if(arr[minIndex] > arr[i]){//如果数组里最小的值大于数组的任意一个数
					minIndex = i;			//最小值为i
				}
			}
			if(arr[minIndex] !== arr[0]){	//如果数组最小的值不等于第一位
				temp = arr[minIndex];		//把最小的值给容器
				arr[minIndex] = arr[0];		//数组第一位赋值给之前最小值的容器
				arr[0] = temp;				//最小的值赋值给数组第一位之前的容器
			}								//这是运算把最小的值放在最前面
			console.log(arr);
			
			for(var j = 0; j < arr.length - 1; j ++){	//这一步是循环j,j是比数组少一位[4,38,3,5,8,2,]
				minIndex = j;							//最小值为j
				console.log( j);
				for(var i = j + 1; i < arr.length; i ++){ //这是循环i,i是比j多一位数[38,3,5,8,2,1]
					if(arr[minIndex] > arr[i]){			//如果数组里最小的值大于数组的任意一个数
						minIndex = i;					//那么最小值为i
					}									//意思就是每次循环拿i最小的值和j的数组比,如果i比j小则换位,
				}
				if(arr[minIndex] !== arr[j]){
					temp = arr[minIndex];
					arr[minIndex] = arr[j];
					arr[j] = temp;
				}
				console.log("arr===>" + arr);
			}
			console.log(arr);


```

+递归思想

```
function fn(n){
				if(n === 2 || n === 1){
					return 1;				//判断,如果fn(n),n的值是fn(1)或fn(2);
				}							//则不判断后,都变成1
				// n = n-1 + n-2
				return fn(n-1) + fn(n-2);			//F[n]=F[n-1]+F[n-2]  (n>=3,F[1]=1,F[2]=1) 
			}									
													//1,1,2,3,5,8,13,21,34,55,89,144,从第三个开始,每个数都等于前两个数相加
			console.log("兔子====>" + fn(6));	
// 			fn(6) ==> 	fn(5) + fn(4)		//"fn(6)从6开始 6-1=5那么 fn(5)" + "6-2=4那么 fn(4)"
// 				  ==>	fn(4)+fn(3) + fn(3)+fn(2)		// "5-1=4那么 fn(4)" + "5-2=3那么 fn(4)" + "4-1=3那么 fn(3)" + "4-2=2那么 fn(2)"
// 				  ==>   fn(3)+fn(2)+fn(2) + fn(1)+fn(2)+fn(1)+fn(1)		//依次类推
			   // ==>	fn(2)+fn(1) +fn(2)+fn(2) + fn(1)+fn(2)+fn(1)+fn(1)	//差不多每次换算到fn(2)和fn(1)都是1,再把他们加起来就是了
```
## 今天就到这里了