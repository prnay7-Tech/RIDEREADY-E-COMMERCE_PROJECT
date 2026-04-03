# RIDEREADY-E-COMMERCE_PROJECT
Building a RideReady e-commerce website using MERN stack can provide a seamless experience for customers to browse and purchase bike/cycle gear and accessories. With React, you can create a dynamic and responsive frontend, while Node.js and Express handle backend APIs for product listings, cart management, and user authentication and others.

// console.log("Mern Electronic Ecommerce API")
import express from 'express'
import mongoose from 'mongoose';
import bodyParser from 'express' // after thunder
import userRouter from './Routes/user.js'
import productRouter from './Routes/product.js'
import cartRouter from './Routes/cart.js'
import addressRouter from './Routes/address.js'
import cors from 'cors'

const app = express()
//after thunder error
app.use(bodyParser.json())





app.use(cors({
    origin:true,
    methods:["GET","POST","PUT","DELETE"],
    credentials:true
}))





//after routes
//user Router
app.use('/api/user',userRouter)
 // api/user/register

 //product router
 app.use('/api/product',productRouter)

 //cart Router

 
 app.use('/api/cart',cartRouter)

 //address Router
 app.use('/api/address',addressRouter)



mongoose.connect("mongodb://localhost:27017/",{
    dbName:"Pranay_16"
}
).then(()=>console.log("Mongodb Connected Successfully..!")).catch((err)=>console.log(err));



const port = 1000;
app.listen(port,()=>console.log("Server is running on port ${port}..!)"))
