# Testing Out GitHub
**Print out Graph**
*Graph shows change in beta was W/L is changed*
> The current amplification factor β of a BJT is very sensitive to the base width as well as to the ratio of the base doping to the emitter doping. Calculate and plot β for a p-n-p BJT with L′ₚ = Lⁿₚ for:
1. (a) nₙ = pₚ, W_b / L′ₚ = 0.01 to 1;
2. (b) W_b = Lⁿₚ, nₙ / pₚ = 0.01 to 1.

---------------------------------------------
' #include <iostream>
#include <iomanip>
using namespace std;
 
int main(){ 
    const double alpha_Tb = 0.5;
 
 for( double r = .01; r<=1.0; r+=.01) { 
    double gamma = 1.0/(1.0+r);
    double alpha = gamma * alpha_Tb;
    double beta = alpha/(1.0-alpha);


    cout<<r << " " << beta << "\n";
 }
const double gamma_a = 0.5;   // n_n = p_p => gamma = 0.5

    cout << fixed << setprecision(5);
    cout << "x = Wb/L\tbeta(x)\n";

    for (double x = 0.01; x <= 1.0001; x += 0.01) {
        double alpha_T = 1.0 - 0.5 * x * x;   // alpha_T(x) = 1 - x^2/2
        double alpha   = gamma_a * alpha_T;   // alpha = gamma * alpha_T
        double beta    = alpha / (1.0 - alpha);

        cout << x << "\t" << beta << "\n";
    }


 return 0;
} ' 

- code defines constants
- then use loop to increase the value of W/L from .01 to 1
- then use the gamma defined in loop to set other constants

<img width="544" height="323" alt="PicofBetaGraph" src="https://github.com/user-attachments/assets/3d3bfc50-6943-4b9e-b821-2b258cd8e8de" />

[Textbook Problem is From](https://rrsdce.wordpress.com/wp-content/uploads/2018/07/sspd-eee-swapnil.pdf)




