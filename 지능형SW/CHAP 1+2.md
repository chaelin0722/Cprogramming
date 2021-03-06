### intelligence software에서

definition of AI  => **acting rationally**..

그렇다면 **Rational하다는 기준은?**

#### 4가지 지표가 있다.

1.  **performance measure** that defines the criterion of success
2.  agent's **prior knowledge** of the environment
3.  the **actions** that the agent can perform
4. the agent's **percept sequence** date



## 단!

agent는 전지전능하지 않다. 우리는 합리성과 전지성을 구분해야 한다. 

초기 agent는 prior knowledge에 따라 행동하고 환경으로 부터 계속 sequence percept가 늘어난다. 따라서 점점 더 합리적으로 행동할 수 있게 되는 것이다.

따라서 주어진 정보 속에서 최대한 performance measure이 최대화 하는 방향의 action을 취하게 되는 것이다.



### 7 properties of task environment

1. fully observable  **vs** partially observable.

   > 주어진 환경에 대한 정보를 전부 다 정확히 아느냐 모르느냐..

2. deterministic **vs** stochastic

   > 지금 현 state 에서 어떤 action을 취했을 때, 어떤 next state가 나올지 아느냐 모르느냐~

3. single agent **vs** multi agent

   > agent의 갯수가 1개 이상이느냐의 차이! multi agent의 경우 cooperative multi agent, competitive multi agent가 있다.

4. discrete **vs** continuous

   > 지금 택한 action이 다음 state에 영향을 미칠지 

5. known **vs** unknown

   > 모든 action에 대해 어떤 next state가 나올지 전부 아는 것!  ==> determiistic은 지금 현 state만!

6.  episodic **vs** sequential

   > 각 state들이 독립적인지, 독립적이지 않고 영향을 미치는지

7.  static **vs** dynamic

   > 주어진 환경의 변화가 있고 없고!





### agent의 목표는 performance measure가 극대화 되길 기대하는 방향으로 action을 선택하는 것이다.

자세히!

### rational agent는 갖고 있는 sequence of percept와 prior knowledge를 갖고 expected to maximize performance measure하는 방향을 취하는 action을 선택한다. 이 action은 agent function에서 정해지게 된다..

> (simple, model reflex -> condition-action rule에 의해, goal->goal, utility->utility rule에 의해 action이 정해질 것)



#### agent function != agent program

agent function이 추상적인 개념이라면 agent program은 이 개념을 실제로 프로그래밍 한 것이다. 아래 agent program 4가지를 보자



<hr>

#### agent program 4가지

- simple-reflex based agent

  > current percept 만 갖고 condition-action rule을 통해 action을 선택한다.

  단점 : partially observable 한 환경에서는 잘 동작하지 못한다.. 이를 커버하는게 model-based reflex agent

  

- model-reflex based agent   => 얘가 좀 complicated함

  > partially observable한 문제를 해결하기 위해 internal state를 계속 유지한다 
  >
  > 이 agent 에서는 지금 받아들인 current state가 partially observable 하기 때문에 현재 인식된 정보(current state)와 internal state 그리고 model을 고려해 update 된 current state로 판단해 action을 선택한다. 이때에도 condition-action rule을 통해 action 선택! 여기의 conditino에 update된 current state를 주어주는 것이다. 

  * internal state : 지금 주변 환경에서 일어나는 일들을 (percept history)들을 계속 유지한다. 

    또한, 아래의 두 모델로 인해 update 되는데,  주변 환경의 진화, 변화(model_1)와 어떠한 action에 대한 결과가 어떻게 나오는지(model_2)에 대한 정보를 통해 매번 update 된다. 

  - model 
    1. How world evolves
    2. what my actions do



- goal-based agent

  > action을 선택할 때, goal 이 무엇인지에 따라 action을 판단하게 된다. 
  >
  > 대부분의 문제는 단순하지 않기 때문에 하나의 goal을 달성하기 위해서는 하나 이상의 action을 연속적으로 수행해야 한다. 따라서 goal 을 a sequence of actions 라고도 한다. 

#### goal == a sequence of action



- utility-based agent 

  > utility는 많은 요소를 함께 고려해야 한다. 따라서 상충되는 goal들에 대한 절충안도 마련이 가능하다.
  >
  > partially observable하고 stochasticity 는 실제 환경에서 만연하다 그러므로 우리는 불확성의 전제 하에 판단을 내려야 한다. 
  >
  > ==> 따라서 expected-utility of the action outcomes 를 최대화 할 수 있는 action을 찾아야 한다.

  

- learning agent 

  >  새로운 것을 학습해 자신의 지식을 향상시킨다!		
  >
  > 위의 agent progrma을 갖고 critic-> learning  element -> program generator(exploratory action)을 통해 action을 선택하는 과정을 수행한다.
  >
  > 
  >
  > critic -> current state 에 대한 feedback 제공
  >
  > learning elemnt -> given feedback으로 어떤 판단을 해야할지 어떤게 더 나은 미래를 만들지 판단한다.
  >
  > 마지막으로 program generator이 작동! 이때..!! exploratoryaction이라는 것을 통해 약간의 변화를 주는 랜덤행동으로 action을 랜덤하게 취한다. 
