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

## 路由器配置
> mobileApp.config(function($stateProvider, $urlRouterProvider){
>>        $stateProvider.state("home",{
            url : "/home",
            templateUrl : "./web/app/templ/home.html"
        }).state("other",{
            url : "/other",
            templateUrl : "./web/app/templ/other.html"
        });
>>        $urlRouterProvider.otherwise('/home');
>    });

## 导航
> 页面导航 
>> <ion-nav-bar class="bar-positive" align-title="center">           
            <ion-nav-back-button></ion-nav-back-button>	
   </ion-nav-bar>
>> 视图 
>  <ion-nav-view></ion-nav-view>
