//Day 10 Vite and setting up custom configuration

Customized ESLint (.eslintrc.cjs)

Integrated vite-plugin-eslint

Installed and prepped React Router DOM


//Day 11 Learned how we can set up a simple SPA with React-router-dom. 

//CSS
Its a tradition to make a module.css for each component to reduce the class conflict.
each component gets an import of corresponding css. These css are named exactly as components name but with extension of module.

for example Pricing.jsx has css module of pricing.module.css
the css is then imported as style from './location/pricing.module.css'

when applying the css we simply extract the class by the objection selection method in js {style.classname};

so if css has 

a.siteLinks{}

and we do 

{style.siteLinks}

on that component we will have a.siteLinks_XYZ value attached, this is called scoped class.

The new style is now attached to the sites dom with <Style> tag and now even if a.siteLink is defined somewhere we get

a.siteLink_XYZ.


//Routing.
In react we can import Component functions like BrowserRouter -> Routes and -> Route from library or package called react-router-dom. This wraps the entire application and enables react to manage the routing.  We do this by wrapping everything in App function

function App(){
    return (
        <BrowserRouter>
             <Routes>
                <Route path="/" element={<Homepage></Homepage>}></Route>
                <Route path="product" element={<Product></Product>}></Route>
                <Route path="pricing" element={<Pricing></Pricing>}></Route>
                <Route path="app" element={<AppLayout></AppLayout>}></Route>
                <Route path="login" element={<Login></Login>}></Route>
                <Route path="*" element={<PageNotFound></PageNotFound>}></Route>
            </Routes>
    </BroswerRouter>
    )
}

there will be each components defined for example
<HomePage>

import styles from "./Homepage.module.css";
import {Link} from 'react-router-dom';
import PageNav from '../components/PageNav'

export default function Homepage() {
  return (
    <main className={styles.homepage}>
      <PageNav></PageNav>
      <section>
        <h1>
          You travel the world.
          <br />
          WorldWise keeps track of your adventures.
        </h1>
        <h2>
          A world map that tracks your footsteps into every city you can think
          of. Never forget your wonderful experiences, and show your friends how
          you have wandered the world.
        </h2>
        <Link to='/app' className="cta">Start Tracking now</Link>
      </section>
    </main>
  );
}


//Links Vs NavLinks 

Components Provided by 'react-router-dom' to navigate pages.

<Links to=""> and <NavLinks to=""> both reqires to="" props passed into it.

<Links> return a simple <a> and prevents the default browser behavior of reloading, which you may remember
from js courses we do it by doing btn.addEventListener('click',function(e)=>{e.preventDefault()});

<a href="/about">About</a>

<NavLinks> on the other hand is designed for navigation menus where we want to highlight active links.
An "active" clas is automatically assigned to the current url that matches the prop.

<a href="/about" class="active">About</a>