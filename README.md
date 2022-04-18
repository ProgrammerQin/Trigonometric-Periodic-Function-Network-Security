# Trigonometric_Periodic_Function_For_Network_Security

Part A: Modeling login attempts
You are a computational expert who is working for a network security firm. The security analyst in your
group is monitoring the login attempts of a server for a client. She notices that between midnight and 6
am there is a variation in the number of attempts and wants to model the data. With such modeling we
can do some resource allocation and address the issues. You are the only one on the team with
programming abilities and so the team is counting on you. The login data, 𝜙(n,t), is a function of login
attempts (n) and time (t). . However, for ease of handling the data is presented to you via a
transformation, and therefore as a function of time alone (S(t)). The data is handed to you in a file
A04_sfwr_data_01.txt. In S(t), a large negative number implies a low login attempt and positive
value implies a high attempt. The 120 data points are a function of time as well. For the convenience of
plotting and analyzing, the time data, t, is in the interval [0,120]. Further, the security analyst can tell
you that this data is periodic.
An equation that you propose to use to model the data is
𝑆)(𝑡) = − /𝐴 sin /!"
# 𝑡4 + 𝜇4 𝑒$%!"
# &'   (1)
Where 𝑆)(𝑡)represents the estimated value of the login attempts, T is the time period of the data, 𝜇 is
some mean, and A and B are constants. It is believed that the three values, 𝜇 , A and B are in the interval
[0,2]. The objective is to determine these values such that the model 𝑆)(𝑡) matches S(t) as closely as
possible. To evaluate the closeness of this fit, you decide to use the mean square error as
𝑀𝑆𝐸 = )
* ∑ <𝑆)(𝑡) − 𝑆(𝑡)=!*
&+) , (2)
With the above model and metrics in place, you want to do the following:
1. The data from the file A04_sfwr_data_01.txt is loaded using the getInputs() function and is
stored in the array S_true.
2. Define the time period, T, of the signal based on the information given above. Define the range
of the parameters, 𝜇 , A and B using the variable names mu, A and B. These definitions should be
through the setParameters() function.
3. Conduct a brute force search over these parameters’ range to find out the optimal combination
of mu, A and B that results in a MSE of less than 1.0. This searching is done through the getFit()
function. The function evaluateModel() is used to calculate equation (1) for each combination of
these parameters.
Hint: For the search, use small variations of upto 0.05 for these parameters.
S. Srinivasan
Copyright © ssriniv@mcmaster.ca
4. The getFit() function also keeps track of how the MSE has been reducing over the search in the
array MSE_trend.
5. The pseudo code of main program is structured as follows:
getInputs()
setParameters()
getFit()
print the optimal values of mu, A and B
print the mse
plot results
The output should be printed only from the main program.
Your program output should be in the following format:
Test Case 1: (Note: your data in the file is different from the one shown here.)
The value of A is: 1.00
The value of B is: 0.50
The value of mu is: 0.90
The MSE predicted by our model is: 0.899
Part B: Some variation is observed!
While the model seemed to work and your firm was able to minimize the intrusion attempts with some
security measures, the hackers decided to evolve their attempts pattern. As a result, the above model no
longer worked optimally. Your colleagues rush to you with a new data set (A04_sfwr_data_03.txt)
for which the model was not very optimal. They want you to minimize the MSE further.
You decide to use a slightly modified model by introducing an additional parameter C. This way you can
reuse most of the code as well! This refined model is
𝑆)(𝑡) = − /𝐴 sin /!"
# 𝑡4 + 𝜇4 𝑒$,
!"
# $
% - 
  (3)
This parameter C is also in the range [0, 2]. With this definition, you want to optimize the model in
Equation (3) using the same 5 steps as in part A. Further, you decide to use a refined benchmark of MSE
for convergence, i.e., MSE<=0.5. In addition to the other data that was being printed, the pseudocode will
now print the optimal value of the parameter C as well.
S. Srinivasan
Copyright © ssriniv@mcmaster.ca
Once again, the output should be printed only from the main program.
Your program output should be in the following format:
Test Case 2: (Note: your data in the file is different from the one shown here.)
The value of A is: 1.00
The value of B is: 0.50
The value of C is: 1.30
The value of mu is: 0.90
The MSE predicted by our model is: 0.225
Part C: Towards a generic model
Within days of the revised model, you are told that the pattern of attempts is modified a bit. Your
colleague wants to know if there is a way to enhance the model and improve the accuracy further, i.e.,
even smaller MSE value. Since this client is very critical for the company, you decide to take on the
challenge. After much deliberation, you propose to use the following equation:
𝑆)(𝑡) = − /𝐴 sin /!"
# 𝑡 + 𝛿4 + 𝜇4 𝑒$,
!"
# $&'
% - 
  (4)
You introduce a new parameter, d that is in the range [0,1.5]. In your program you call this variable
shift. The new dataset is given to you in the file A04_sfwr_data_05.txt. As before, you decide to
undertake the brute force search using almost the same pseudocode to optimize the parameters in
Equation (4). This time you set an even stringent benchmark for yourself, MSE <=0.1. You want your
code to print the optimal values of all the parameters.
Once again, the output should be printed only from the main program.
Your program output should be in the following format:
Test Case 3: (Note: your data in the file is different from the one shown here.)
The value of A is: 1.00
The value of B is: 0.20
The value of C is: 1.30
The value of mu is: 0.90
S. Srinivasan
Copyright © ssriniv@mcmaster.ca
The value of shift is: 0.80
The MSE predicted by our model is: 0.042
Submission Requirements: Submit a single word or PDF file containing the python program for each
part along with the corresponding sample screenshots of the output when you run the program, to the
dropbox titled A04 in the Assignments section on Avenue. Do not submit a screenshot of the program
itself. This will result in a grade of 0. Copy and paste your code into a text editor such as MS word
