<template>
    <div class="quiz-section-box">
        <div class="progressbar">
            <div class="bar"></div>
        </div>
        
            <transition>
                <div v-if="slide==0">
                    <div v-for="(i,index) in ques1" :key="index">
                        <div class="questions">
                            <h1>{{i.question}}</h1>
                            <div class="options">
                                <h3> AGREE</h3>
                                <div class="agree" @click="addclass1(i.options,index)">

                                </div>
                                <div class="neutral" @click="addclass2(i.options,index)">

                                </div>
                                <div class="disagree" @click="addclass3(i.options,index)">


                                </div>
                                <h3> Disagree</h3>
                            </div>

                        </div>

                    </div>

                </div>
                <div v-else-if="slide==1">
                    <div v-for="(i,index) in ques2" :key="index">
                        <div class="questions">
                            <h1>{{i.question}}</h1>
                            <div class="options">
                                <h3> AGREE</h3>
                                <div class="agree" @click="addclass1(i.options,index)">

                                </div>
                                <div class="neutral" @click="addclass2(i.options,index)">

                                </div>
                                <div class="disagree" @click="addclass3(i.options,index)">


                                </div>
                                <h3> Disagree</h3>
                            </div>

                        </div>

                    </div>

                </div>
                <div v-else-if="slide==2">
                    <div v-for="(i,index) in ques3" :key="index">
                        <div class="questions">
                            <h1>{{i.question}}</h1>
                            <div class="options">
                                <h3> AGREE</h3>
                                <div class="agree" @click="addclass1(i.options,index)">
                                </div>
                                <div class="neutral" @click="addclass2(i.options,index)">
                                </div>
                                <div class="disagree" @click="addclass3(i.options,index)">
                                </div>
                                <h3> Disagree</h3>
                            </div>

                        </div>

                    </div>
                </div>
            </transition>

                <button @click="submit" class="submit">{{buttonvalue}}</button>
    </div>
</template>
<script>
export default {
    name: 'quiz-section',
    data(){
        return{
            answers0:[],
            answers1:[],
            answers2:[],
            buttonvalue:"next",
            slide:0,
            ques1:[
                {
                    question:" are u a good listener",
                    options: [{ a: "I'm not sure, that's a good question. The distinction between the two is so dependant on perception" , b: "One time my parents were fighting over my dad's affair and my dad pushed my mom. The fall broke her" ,c:"No. If you neglect them, your finances will always be burning on the back of every decision you mak"}],
                },
                 {
                    question:"are u a good orator",
                     options: [{ a:"I actually have that on my playlist! Hey ENFPs. I've posted this thread on the philosophy board too, but I am really curious to reading" ,b:"less introvert",c:"ambivert"}],
                    
                },
                {
                    question: "are you a good communicator",
                    options: [{ a: "I'm not sure, that's a good question. The distinction between the two is so dependant on perception" , b: "One time my parents were fighting over my dad's affair and my dad pushed my mom. The fall broke her" , c: "No. If you neglect them, your finances will always be burning on the back of every decision you mak" }],
                },
                {
                    question:"Seeing other people",
                    options: [{ a: "I'm not sure, that's a good question. The distinction between the two is so dependant on perception" , b: "One time my parents were fighting over my dad's affair and my dad pushed my mom. The fall broke her" , c: "No. If you neglect them, your finances will always be burning on the back of every decision you mak" }],
                },
                {
                    question:"You often make a backup plan for a backup plan.",
                    options: [{ a: "I'm not sure, that's a good question. The distinction between the two is so dependant on perception" , b: "One time my parents were fighting over my dad's affair and my dad pushed my mom. The fall broke her" , c: "No. If you neglect them, your finances will always be burning on the back of every decision you mak" }],

                }
            ],
            ques2: [
                {
                    question: "hello",
                    options: [{ a: "I'm not sure, that's a good question. The distinction between the two is so dependant on perception", b: "One time my parents were fighting over my dad's affair and my dad pushed my mom. The fall broke her", c: "No. If you neglect them, your finances will always be burning on the back of every decision you mak" }],
                },
                {
                    question: "are u a good orator",
                    options: [{ a: "I actually have that on my playlist! Hey ENFPs. I've posted this thread on the philosophy board too, but I am really curious to reading", b: "less introvert", c: "ambivert" }],

                },
                {
                    question: "are you a good communicator",
                    options: [{ a: "I'm not sure, that's a good question. The distinction between the two is so dependant on perception", b: "One time my parents were fighting over my dad's affair and my dad pushed my mom. The fall broke her", c: "No. If you neglect them, your finances will always be burning on the back of every decision you mak" }],
                },
                {
                    question: "Seeing other people cry can .",
                    options: [{ a: "I'm not sure, that's a good question. The distinction between the two is so dependant on perception", b: "One time my parents were fighting over my dad's affair and my dad pushed my mom. The fall broke her", c: "No. If you neglect them, your finances will always be burning on the back of every decision you mak" }],
                },
                {
                    question: "noice",
                    options: [{ a: "I'm not sure, that's a good question. The distinction between the two is so dependant on perception", b: "One time my parents were fighting over my dad's affair and my dad pushed my mom. The fall broke her", c: "No. If you neglect them, your finances will always be burning on the back of every decision you mak" }],

                }

            ],
            ques3: [
                {
                    question: "slide =2",
                    options: [{ a: "I'm not sure, that's a good question. The distinction between the two is so dependant on perception", b: "One time my parents were fighting over my dad's affair and my dad pushed my mom. The fall broke her", c: "No. If you neglect them, your finances will always be burning on the back of every decision you mak" }],
                },
                {
                    question: "are u a good orator",
                    options: [{ a: "I actually have that on my playlist! Hey ENFPs. I've posted this thread on the philosophy board too, but I am really curious to reading", b: "less introvert", c: "ambivert" }],

                },
                {
                    question: "are you a good communicator",
                    options: [{ a: "I'm not sure, that's a good question. The distinction between the two is so dependant on perception", b: "One time my parents were fighting over my dad's affair and my dad pushed my mom. The fall broke her", c: "No. If you neglect them, your finances will always be burning on the back of every decision you mak" }],
                },
                {
                    question: "Seeing other people .",
                    options: [{ a: "I'm not sure, that's a good question. The distinction between the two is so dependant on perception", b: "One time my parents were fighting over my dad's affair and my dad pushed my mom. The fall broke her", c: "No. If you neglect them, your finances will always be burning on the back of every decision you mak" }],
                },
                {
                    question: "over.",
                    options: [{ a: "I'm not sure, that's a good question. The distinction between the two is so dependant on perception", b: "One time my parents were fighting over my dad's affair and my dad pushed my mom. The fall broke her", c: "No. If you neglect them, your finances will always be burning on the back of every decision you mak" }],

                }

            ]
          
        }
    },
    methods:{

        addclass1(i,index){
            
            if(document.getElementsByClassName('agree')[index].classList.contains('active')){
                document.getElementsByClassName('agree')[index].classList.remove('active');
                if (this.slide == 0) {
                    this.answers0[index] = "";
                }
                else if (this.slide == 1) {
                    this.answers1[index] = "";
                }
                else if (this.slide == 2) {
                    this.answers2[index] = "";
                }
            }
            else{
                if (this.slide == 0) {
                    this.answers0[index] = (i[0].a);
                }
                else if (this.slide == 1) {
                    this.answers1[index] = (i[0].a);
                }
                else if (this.slide == 2) {
                    this.answers2[index] = (i[0].a);
                }

            document.getElementsByClassName("agree")[index].classList.add('active');
            document.getElementsByClassName("neutral")[index].classList.remove('active');
            document.getElementsByClassName("disagree")[index].classList.remove('active');
            }
          

        },
        addclass2(i,index){  

            if (document.getElementsByClassName('neutral')[index].classList.contains('active')) {
                document.getElementsByClassName('neutral')[index].classList.remove('active');
                if(this.slide==0){
                    this.answers0[index] = "";
                }
                else if(this.slide==1){
                    this.answers1[index] = "";
                }
                else if(this.slide==2){
                    this.answers2[index] = "";
                }


            }
            else{
                if(this.slide==0){
                    this.answers0[index]=(i[0].b);
                }
                else if(this.slide==1){
                    this.answers1[index]=(i[0].b);
                }
                else if(this.slide==2){
                    this.answers2[index]=(i[0].b);
                }
            document.getElementsByClassName("neutral")[index].classList.add('active');
            document.getElementsByClassName("agree")[index].classList.remove('active');
            document.getElementsByClassName("disagree")[index].classList.remove('active');
            }
          
           
            },
        addclass3(i,index){
            if (document.getElementsByClassName('disagree')[index].classList.contains('active')) {
                document.getElementsByClassName('disagree')[index].classList.remove('active');
                if (this.slide == 0) {
                    this.answers0[index] = "";
                }
                else if (this.slide == 1) {
                    this.answers1[index] = "";
                }
                else if (this.slide == 2) {
                    this.answers2[index] = "";
                }
            }
            else{
                if (this.slide == 0) {
                    this.answers0[index] = (i[0].c);
                }
                else if (this.slide == 1) {
                    this.answers1[index] = (i[0].c);
                }
                else if (this.slide == 2) {
                    this.answers2[index] = (i[0].c);
                }
            document.getElementsByClassName("neutral")[index].classList.remove('active');
            document.getElementsByClassName("agree")[index].classList.remove('active');
            document.getElementsByClassName("disagree")[index].classList.add('active');
            }
            },
        submit(){
            window.scrollTo(0,0);
            if(this.slide<2){
                if(this.slide==1){
                    this.buttonvalue="submit";
                    document.getElementsByClassName('bar')[0].style.width = "27vw";
                    this.slide += 1;
                }
                else{
                    document.getElementsByClassName('bar')[0].style.width= "13vw";
                    this.slide+=1;
                }
                return;
            }
            if(this.buttonvalue=="submit"){
            document.getElementsByClassName('bar')[0].style.width = "40vw";
            const answers= this.answers0.concat(this.answers1,this.answers2);
            var dataans="";
            for(var i=0;i<answers.length; i++){
                if(answers[i]===""){
                }
                else{
                    dataans+=answers[i]+" ";
                }
            }
            
            // for(var j=0;j<this.answers.length;j++){
            //     if(this.answers[j]===null || this.answers.length!==(this.ques3.length)){
            //         alert("please answer all questions");
            //         return;
            //     }
            // }
            // if(this.answers0 === [] || this.answers.length === 0 || this.answers === 'undefined' || this.answers.length==''){
            //     alert("please answer all questions");
            //     return;
            // }
            // else{
                this.$router.push({ name: 'personality', params: { dataans: dataans } });
            // }
        }
        }
    }
}
</script>
<style>




.progressbar{
    background-color: #ffc107;
    width: 40vw;
    height: 10px;
    border-radius: 5px;
    margin:10px;
    display:flex;
    justify-content:center;
    align-items:flex-start;
    flex-direction: column;
    padding: 3px;
}
.bar{
    background-color: #060b6a;
    width: 5px;
    height: 10px;
    border-radius: 5px;
    transition: all 0.3s ease-in-out;
}

html{
    scroll-behavior: smooth;
}


.questions{
    display:flex;
    flex-direction:column;
    justify-content:center;
    align-items:center;
    align-content: center;

}

.quiz-section-box{
    background-color: #05386B;
    display:flex;
    flex-direction:column;
    justify-content:center;
    align-items:center;
    padding:0;
    margin:0;
    width:100vw;
    align-content: center;
   
    
}

.submit{
    background-color:#05386B;
    color:#EDF5E1;
    border: none;
    padding: 10px;
    font-size: 20px;
    cursor: pointer;
    margin-top: 10px;
    transition:all 0.3s ease-in-out;
    border-radius:5px;
    border:2px solid #EDF5E1;
}
.submit:hover{
    background-color: #EDF5E1;
    color: #05386B;
}
.options{
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;

}
.agree,.neutral,.disagree{
    background-color: #5CDB95;
    color: #EDF5E1;
    border: none;
    margin: 10px;
    font-size: 20px;
    cursor: pointer;
    margin-top: 20px;
    margin-left:10px;
    border-radius: 50%;
    transition:all 0.25s ease-in-out;
}
.agree:hover,.neutral:hover,.disagree:hover{
    background-color: #EDF5E1;
}
.agree{
    width:50px;
    height:50px;
}
.disagree {
    width: 50px;
    height: 50px;
}
.neutral {
    width: 30px;
    height: 30px;
}
.active {
    background-image:linear-gradient(to right, rgb(255, 240, 240), #5CDB95, rgb(108, 223, 229));
    background-position: left;
    background-size: 300%;
    display: flex;
    justify-content: center;
    align-items: center;
    transition:all 0.5s ease-in-out;
    }
.active::before{
    transition:all 0.5s ease-in-out;
    content: "T";
    position: absolute;
    color:#05386B;
    padding:10px;
    font-size: 30px;
    z-index:100;
}
.active:hover{
    background-position: right;
    
}
</style>
