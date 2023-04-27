<script>
import ForgotPassword from './pages/ForgotPassword.svelte'
import { Router, Route } from 'svelte-routing'
import Home from "./pages/Home.svelte"
import Login from "./pages/Login.svelte"
import Signup from "./pages/Signup.svelte"
import Index from './pages/Index.svelte'



</script>


<Router>
<Route path="/" component={Index} />
<Route path="/login" component={Login} />
<Route path="/signup" component={Signup} />
<Route path="/forgotPassword" component={ForgotPassword} />
<Route path="/home" component={Home} />
</Router>



