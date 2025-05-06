Routes, 

Browser route is most of the time used in root level of the application and the route is also defined on the root level of the application,
Route need a path="" and that path needs to be set without / -> which means its a relative path to the parent route.

Quick refresher

A link="/Somewhere"

will result in 

If we are in home then sitename/somewhere, we we are inside some another page then home/someanohterpage/somewhere. This is relative path.

but link="somewhere"

always result in

Sitename/somewhere 

Outlet

<Outlet /> is like a placeholder or slot in the parent component. Hence a reference to {children} prop.

The child routes you define (like profile, settings, etc.) act like the "cases" in a switch.

React Router automatically chooses which component to render into the <Outlet /> based on the URL.

So <Outlet /> doesn’t do the switching itself — it's just the spot where React Router renders the matched child route.

Outlet is mostly used to render a childroute which is a component that takes only the half of the ui. This means its a way to re-render only parts of a ui. The outlet switches the 
components depending on the child routes defined in the main <BrowswerRouter>


<Outlet /> works only in the context of the parent route it belongs to. It renders whatever child route (or nested route) matches under that specific parent.

For example 
<Route path="dashboard" element={<DashboardLayout />}>
  <Route path="profile" element={<Profile />} />
</Route>

<Route path="account" element={<AccountLayout />}>
  <Route path="security" element={<Security />} />
</Route>

Then:

<Outlet /> in DashboardLayout renders <Profile /> when you're at /dashboard/profile.

<Outlet /> in AccountLayout renders <Security /> when you're at /account/security.

They don't interfere with each other.