# hello_git
this is a sample for git
http://stackoverflow.com/questions/36870505/react-fetch-requires-react-addons-but-there-is-no-react-addons-folder


'use strict';

var React = require('react');

var ExpandableNav = require('../../src/index');
var {ExpandableNavContainer, ExpandableNavbar, ExpandableNavHeader,
    ExpandableNavMenu, ExpandableNavMenuItem, ExpandableNavPage,
    ExpandableNavToggleButton} = ExpandableNav;


var App = React.createClass({
  componentDidMount() {
    $('[data-toggle="menuitem-tooltip"]').tooltip();
  },
  render() {
    var headerSmall = <span className="glyphicon glyphicon-align-justify"></span>;

    var menuItemsSmall = [
      <span className="glyphicon glyphicon-home"></span>,
      <span className="glyphicon glyphicon-user"></span>,
      <span className="glyphicon glyphicon-comment"></span>
    ];
    var menuItemsFull = [
      <div><span className="glyphicon glyphicon-home"></span>  <span>Home</span></div>,
      <div><span className="glyphicon glyphicon-user"></span>  <span>About us</span></div>,
      <div><span className="glyphicon glyphicon-comment"></span>  <span>Contact us</span></div>
    ];
    var headerStyle = {
      paddingLeft: 5
    };
    var fullStyle = {
      paddingLeft: 5
    };
    return (
      <ExpandableNavContainer expanded={true} >
        <ExpandableNavbar fullClass="full" smallClass="small">
          <ExpandableNavHeader small={headerSmall} full={headerSmall} headerStyle={headerStyle} fullStyle={fullStyle}/>
          <ExpandableNavMenu>
            <ExpandableNavMenuItem small={menuItemsSmall[0]} full={menuItemsFull[0]} tooltip={"Home"} jquery={window.$}/>
            <ExpandableNavMenuItem small={menuItemsSmall[1]} full={menuItemsFull[1]} tooltip={"About us"} jquery={window.$} />
            <ExpandableNavMenuItem small={menuItemsSmall[2]} full={menuItemsFull[2]} tooltip={"Contact us"} jquery={window.$}/>
          </ExpandableNavMenu>
        </ExpandableNavbar>
        <ExpandableNavToggleButton smallClass="s" className="shared"/>
        <ExpandableNavPage>
        </ExpandableNavPage>
      </ExpandableNavContainer>
    );
  }
});

module.exports = App;
