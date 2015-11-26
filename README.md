# ionic-webapp

## 加载模块
> angular.module("mobileApp",["ionic"]);

## 模板加载配置
> app.run(['$rootScope', '$state', '$stateParams',"$ionicLoading",<br>
>>        function($rootScope, $state, $stateParams,$ionicLoading) {<br>
            $rootScope.$state = $state;<br>
            $rootScope.$stateParams = $stateParams;<br>
            //视图改变开始时执行事件<br>
            $rootScope.$on('$stateChangeStart', function($scope){<br>
            	//生成加载图片<br>
                $ionicLoading.show({<br>
                    content: '',<br>
                    animation: 'fade-in',<br>
                    showBackdrop: true,<br>
                    maxWidth: 200,<br>
                    showDelay: 0<br>
                });<br>
            });<br>
            $rootScope.$on('$stateChangeSuccess', function($scope){<br>
            	//隐藏加载图片<br>
            	$ionicLoading.hide();<br>
            })<br>
 >>       }<br>
>    ]);<br>

## 获取url参数
> $location.search()['name']; 
  
## jsonp
> $http.jsonp("XXXX?callback=JSON_CALLBACK");
