# Custom React Slider
```
import React, { useState } from 'react'; import albumdata from "../data";

const Home = () => {

const [activeIndex, setActiveIndex] = useState(0);
const activeSlide = albumdata[activeIndex];

const { title , thumbnailUrl} = activeSlide;

const nextHandler = () => {
    if(activeIndex >= albumdata.length-1){
        setActiveIndex(0)
    } else{
        setActiveIndex(preVal => preVal+1)
    }
}
const prevHandler = () => {
    if(activeIndex <= 0){
        setActiveIndex(albumdata.length-1)
    } else{
        setActiveIndex(preVal => preVal-1)
    }
}

return (
    <>
    <div className="container">

        <div className="card"> 
            <h1>{title}</h1>
            <img src={thumbnailUrl} alt="no" />
            <div className="cta">
                <button onClick={prevHandler} >Prev</button>
                <button onClick={nextHandler} >Next</button>
            </div>
        </div>
    </div>
    </>
)
}

export default Home;

```
