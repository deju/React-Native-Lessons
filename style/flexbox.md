## flex布局
参考https://segmentfault.com/a/1190000002658374

- 默认宽度是100%

     <Text style={[styles.text, styles.header]}>
	      根节点上放一个元素，不设置宽度
	  </Text>        

	  <View style={{height: 20, backgroundColor: '#333333'}} />

	  <Text style={[styles.text, styles.header]}>
	      固定宽度的元素上放一个View，不设置宽度
	  </Text> 

	  <View style={{width: 100}}>
	    <View style={{height: 20, backgroundColor: '#333333'}} />
	  </View>

	  <Text style={[styles.text, styles.header]}>
	      flex的元素上放一个View，不设置宽度
	  </Text> 

	  <View style={{flexDirection: 'row'}}>
	    <View style={{flex: 1}}>
	      <View style={{height: 20, backgroundColor: '#333333'}} />
	    </View>
	    <View style={{flex: 1}}/>
	  </View>


	  //测试结果见机器运行 render_div

- 水平/垂直居中
	用alignItems和justijfyContent处理
	
	<Text style={[styles.text, styles.header]}>
        水平居中
    </Text>

    <View style={{height: 100, backgroundColor: '#333333', alignItems: 'center'}}>
      <View style={{backgroundColor: '#fefefe', width: 30, height: 30, borderRadius: 15}}/>
    </View>

     <Text style={[styles.text, styles.header]}>
        垂直居中
    </Text>
    <View style={{height: 100, backgroundColor: '#333333', justifyContent: 'center'}}>
      <View style={{backgroundColor: '#fefefe', width: 30, height: 30, borderRadius: 15}}/>
    </View>

    <Text style={[styles.text, styles.header]}>
        水平垂直居中
    </Text>
    <View style={{height: 100, backgroundColor: '#333333', alignItems: 'center', justifyContent: 'center'}}>
      <View style={{backgroundColor: '#fefefe', width: 30, height: 30, borderRadius: 15}}/>
    </View>


    // see render_center

 - 网格布局

 	等分
 	<View style={styles.flexContainer}>
      <View style={styles.cell}>
        <Text style={styles.welcome}>
          cell1
        </Text>
      </View>
      <View style={styles.cell}>
        <Text style={styles.welcome}>
          cell2
        </Text>
      </View>
      <View style={styles.cell}>
        <Text style={styles.welcome}>
          cell3
        </Text>
      </View>
    </View>

    styles = {
        flexContainer: {
            // 容器需要添加direction才能变成让子元素flex
            flexDirection: 'row'
        },
        cell: {
            flex: 1,
            height: 50,
            backgroundColor: '#aaaaaa'
        },
        welcome: {
            fontSize: 20,
            textAlign: 'center',
            margin: 10
        },
    }

    // see render_flex_1



    左右固定，中间flex

    <View style={styles.flexContainer}>
      <View style={styles.cellfixed}>
        <Text style={styles.welcome}>
          fixed
        </Text>
      </View>
      <View style={styles.cell}>
        <Text style={styles.welcome}>
          flex
        </Text>
      </View>
      <View style={styles.cellfixed}>
        <Text style={styles.welcome}>
          fixed
        </Text>
      </View>
    </View>

    styles = {
        flexContainer: {
            // 容器需要添加direction才能变成让子元素flex
            flexDirection: 'row'
        },
        cell: {
            flex: 1,
            height: 50,
            backgroundColor: '#aaaaaa'
        },
        welcome: {
            fontSize: 20,
            textAlign: 'center',
            margin: 10
        },
        cellfixed: {
            height: 50,
            width: 80,
            backgroundColor: '#fefefe'
        } 
    }

    // see render_flex_2

    嵌套网格

    <Text style={[styles.text, styles.header]}>
	    嵌套的网格
	  </Text>
	  <View style={{flexDirection: 'row', height: 200, backgroundColor:"#fefefe", padding: 20}}>
	    <View style={{flex: 1, flexDirection:'column', padding: 15, backgroundColor:"#eeeeee"}}>  
	        <View style={{flex: 1, backgroundColor:"#bbaaaa"}}>  
	        </View>
	        <View style={{flex: 1, backgroundColor:"#aabbaa"}}>
	        </View>
	    </View>
	    <View style={{flex: 1, padding: 15, flexDirection:'row', backgroundColor:"#eeeeee"}}>
	        <View style={{flex: 1, backgroundColor:"#aaaabb"}}>  
	            <View style={{flex: 1, flexDirection:'row', backgroundColor:"#eeaaaa"}}> 
	               <View style={{flex: 1, backgroundColor:"#eebbaa"}}>  
	              </View>
	              <View style={{flex: 1, backgroundColor:"#bbccee"}}>
	              </View> 
	            </View>
	            <View style={{flex: 1, backgroundColor:"#eebbdd"}}>
	            </View>
	        </View>
	        <View style={{flex: 1, backgroundColor:"#aaccaa"}}>
	          <ScrollView style={{flex: 1, backgroundColor:"#bbccdd", padding: 5}}>
	                <View style={{flexDirection: 'row', height: 50, backgroundColor:"#fefefe"}}>
	                  <View style={{flex: 1, flexDirection:'column', backgroundColor:"#eeeeee"}}>  
	                      <View style={{flex: 1, backgroundColor:"#bbaaaa"}}>  
	                      </View>
	                      <View style={{flex: 1, backgroundColor:"#aabbaa"}}>
	                      </View>
	                  </View>
	                  <View style={{flex: 1, flexDirection:'row', backgroundColor:"#eeeeee"}}>
	                      <View style={{flex: 1, backgroundColor:"#aaaabb"}}>  
	                          <View style={{flex: 1, flexDirection:'row', backgroundColor:"#eeaaaa"}}> 
	                             <View style={{flex: 1, backgroundColor:"#eebbaa"}}>  
	                            </View>
	                            <View style={{flex: 1, backgroundColor:"#bbccee"}}>
	                            </View> 
	                          </View>
	                          <View style={{flex: 1, backgroundColor:"#eebbdd"}}>
	                          </View>
	                      </View>
	                      <View style={{flex: 1, backgroundColor:"#aaccaa"}}>
	                      </View>
	                  </View>
	                </View>
	                <Text style={[styles.text, styles.header, {color: '#ffffff', fontSize: 12}]}>
	                  {(function(){
	                    var str = '';
	                    var n = 100;
	                    while(n--) {
	                      str += '嵌套的网格' + '\n';
	                    }
	                    return str;
	                  })()}
	                </Text>
	          </ScrollView> 
	        </View>
	    </View>
	  </View>

	  // see render_flex_3



### 绝对定位
	用position：'absolute'来设置
	 <View style={{flex: 1, height: 100, backgroundColor: '#333333'}}>
	    <View style={[styles.circle, {position: 'absolute', top: 50, left: 180}]}>
	    </View>
	  </View>
	  styles = {
	    circle: {
	    backgroundColor: '#fe0000',
	    borderRadius: 10,
	    width: 20,
	    height: 20
	    }
	  }

