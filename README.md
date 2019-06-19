# js-deep-copy-
js 对象的深拷贝




      var obj={
         name:"1111",
         age:123,
         sex:200,
         arrTest:["233","3333",[90,9]]
       }
    
      var obj1={} 
    
       function deepClone(origin,target){
       	 var target=target||{},
       	 toStr=Object.prototype.toString,
       	 arrStr="[object Array]"; 
       	 for(var key in origin){
       	     if(origin.hasOwnProperty(key)){
       	 	   if(origin[key]!==null&& typeof(origin[key])=="object"){
       	 	      if(toStr.call(origin[key])==arrStr){
       	 		    target[key]=[];
       	 		    }else{
       	 		     target[key]={};
       	 		    }
       	 	        deepClone(origin[key],target[key])	
             	     	}else{
             	      target[key]=origin[key]
              	  }
       	     	}	 
       	     	
       	 }   	
       	 	return target
       }
    
