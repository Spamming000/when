Algorithm
1. Identify Components
2. Construct Component Hierarchy Diagram
3. Implement the Static Parts of the WebApp
a) Implement a Component and a Necessary Prop
b) Include it into the Main Application
c) Test the Output
d) Repeat (a) to (e)
4. Identify States and Implement States
5. Add Necessary CSS/ Bootstrap

import React from 'react';
function Beautyadvices(props){
  return <h1>{props.content}</h1>
}
export default Beautyadvices;

Navbar.js
import React from 'react';
import { Link } from 'react-router-dom';
import './Navbar.css';

const Navbar = () => {
  return (
    <nav className="navbar">
      <ul className="nav-list">
        <li><Link to="/">Nykaa</Link></li>
        <li><Link to="/Categories">Categories</Link></li>
        <li><Link to="/Brands">Brands</Link></li>
        <li><Link to="/Luxe">Luxe</Link></li>
        <li><Link to="/Nykaafashion">Nykaa Fashion</Link></li>
        <li><Link to="/Beautyadvices">Beaty Advices</Link></li>
      </ul>
    </nav>
  );
}

export default Navbar;


Nykaa.js
import React from 'react';
import nykaaLogo from '../img/nykaa.jpg';

const Nykaa = () => {
  return (
    <div style={{ textAlign: 'center', marginTop: '50px' }}>
      <img
        src={nykaaLogo}
        alt="nykaa Logo"
        style={{ width: '200px', height: 'auto' }}/>
      <h2>Experience beauty at its finest with Nykaa. Get Up to 50% off Bestsellers. Why pay full price? Exciting deals are just a click away. Easy Returns. Authentic Products. Amazing Offers & Freebies. Brands: Maybelline: Up to 30% Off, Lakme: Up to 30% Off.</h2>
    </div>
  );
}

export default Nykaa;

App.js
import React from 'react';
import { BrowserRouter as Router } from 'react-router-dom';
import { Routes, Route } from 'react-router';
import Navbar from './components/Navbar'; 
import Nykaa from './components/Nykaa'; 
import Categories from './components/Categories'; 
import Brands from './components/Brands'; 
import Luxe from './components/Luxe';
import Nykaafashion from './components/Nykaafashion'; 
import Beatyadvices from './components/Beautyadvices'; 
import C from './components/form';

const App = () => {
  return (
    <Router>
      <Navbar />
      <Routes>
        <Route path="/" element={<Nykaa />} />
        <Route path="/Categories" element={<Categories />} />
        <Route path="/Brands" element={<Brands content="Brands" />} />
        <Route path="/Luxe" element={<Luxe />} /> {/* Add new route */}
        <Route path="/Nykaafashion" element={<Nykaafashion content=""/>} /> {/* Add new route */}
        <Route path="/Beautyadvices" element={<Beatyadvices content="BEAUTY BOOK: Nykaa's digital magazine. NYKAA TV: Master classes by Experts and Vloggers."/>} /> {/* Add new route */}
        
      </Routes>
      <C />
    </Router>
  );
}

export default App;

form.js
import { useState } from "react";

export default function C(){
    const[mail,setMail] = useState('please type message');
    return(
        <>
        <h1>sjdhgf</h1>
        <input type='text' value={mail} onChange={(e)=>setMail(e.target.value)} />
        <h1>Your mail:{mail}</h1>
        </>
    );
}

Bootstrap
import Button from 'react-bootstrap/Button';
import 'react-bootstrap/dist/react-bootstrap.min.css';
function Counterbutton(props) {
  return (<Button variant={props.color} onClick={props.fun} disabled={props.con}>{props.content}</Button>);
}

export default Counterbutton;























navbar.css
.navbar {
    background-color: #e12951;
    color: #fff;
  }
  
  .nav-list {
    list-style-type: none;
    display: flex;
    justify-content: space-around;
    padding: 0;
  }
  
  .nav-list li {
    margin: 0;
  }
  
  .nav-list a {
    color: #fff;
    text-decoration: none;
  }
  
  .nav-list a:hover {
    text-decoration: underline;
  }
  
