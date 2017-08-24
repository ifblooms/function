1. 深度克隆
    ```js
    function deepClone(obj){
      var tem,whats = function(v){
        return Object.prototype.toString.call(v).slice(8,-1);
      };
      if(whats(obj)==='Object'){
        tem = {};
      }else if(whats(obj)==='Array'){
        tem = [];
      }else{
        return obj;
      }
      for(key in obj){
        var one = obj[key];
        if(whats(one)==='Object'||whats(one)==='Array'){
          tem[key] = arguments.callee(one);
        }else{
          tem[key] = one;
        }
      }
      return tem;
    }
    ```
2. 
