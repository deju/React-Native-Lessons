##HTML标签与React组件对比
###渲染组件，需要创建一个大写字母开头的本地变量
    
    var MyComp = React.createClass({/**/});

###渲染HTML，在JSX里使用小写字母开头的标签名

    var myDiv = <div className="cls1" />;  //div为小写标签


##JSX语法转换
    
    var app = <Nav color="yellow" />;
    ==>
    var app = React.createElement(Nav, {color: "blue"});


##注释
    
    var content = (
        <Nav>
        {/*一般注释,用{}包起来*/}
        <Person 
        /*
           多行注释 
        */
        name="jj" //行尾注释
        />
        </Nav>
    );
