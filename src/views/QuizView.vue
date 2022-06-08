<template>
    <div class="quiz-section-box">
        <!-- <button @click="back">go back

        </button> -->
        <KeepAlive>

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

        </KeepAlive>
                <button @click="submit" class="submit">{{buttonvalue}}</button>
    </div>
</template>
<script>
export default {
    name: 'quiz-section',
    data(){
        return{
            answers:[],
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
        back(){
            if (this.slide ==1 || this.slide ==2){
                if(this.slide ==2){
                    this.buttonvalue="next";
                }
                this.slide--;
            }
            else{
                return;
            }
            
        },
        addclass1(i,index){
            
            if(document.getElementsByClassName('agree')[index].classList.contains('active')){
                document.getElementsByClassName('agree')[index].classList.remove('active');
                this.answers[index]="";
            }
            else{
                this.answers[index] = (i[0].a);
            document.getElementsByClassName("agree")[index].classList.add('active');
            document.getElementsByClassName("neutral")[index].classList.remove('active');
            document.getElementsByClassName("disagree")[index].classList.remove('active');
            }
          

        },
        addclass2(i,index){  

            if (document.getElementsByClassName('neutral')[index].classList.contains('active')) {
                document.getElementsByClassName('neutral')[index].classList.remove('active');
                this.answers[index] = "";
            }
            else{
            this.answers[index]=(i[0].b);
            document.getElementsByClassName("neutral")[index].classList.add('active');
            document.getElementsByClassName("agree")[index].classList.remove('active');
            document.getElementsByClassName("disagree")[index].classList.remove('active');
            }
            // this.answers[index]=(this.options[index].b);
          
           
            },
        addclass3(i,index){

            if (document.getElementsByClassName('disagree')[index].classList.contains('active')) {
                document.getElementsByClassName('disagree')[index].classList.remove('active');
                this.answers[index] = null;
            }
            else{
            this.answers[index] = (i[0].c);
            document.getElementsByClassName("neutral")[index].classList.remove('active');
            document.getElementsByClassName("agree")[index].classList.remove('active');
            document.getElementsByClassName("disagree")[index].classList.add('active');
            }
            //this.answers[index] = (this.options[index].c);
            console.log(this.answers);
            },
        submit(){
            if(this.slide<2){
                if(this.slide==1){
                    this.buttonvalue="submit";
                    this.slide += 1;
                }
                else{
                    this.slide+=1;
                }
                return;
            }
            if(this.buttonvalue=="submit"){
            console.log(this.answers);
            
            console.log(this.answers.length);
           

           
            for(var j=0;j<this.answers.length;j++){
                if(this.answers[j]===null || this.answers.length!==(this.ques3.length)){
                    alert("please answer all questions");
                    return;
                }
            }
            if(this.answers === [] || this.answers.length === 0 || this.answers === 'undefined' || this.answers.length==''){
                alert("please answer all questions");
                return;
            }
            else{
                this.$router.push({ name: 'personality', params: { answers: this.answers } });
            }
        }
        }
    }
}
</script>
<style>




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
    background-image:linear-gradient(to right, rgb(255, 240, 240), rgb(0, 255, 217), rgb(255, 255, 0));
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
    padding:10px;
    font-size: 30px;
    color: white;
    z-index:100;
}
.active:hover{
    background-position: right;
    
}
</style>
