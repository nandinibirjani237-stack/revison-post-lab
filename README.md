# revison-post-lab
# task 5
#include <stdio.h>

int main() {
float mobile_load,discount=0.0,payable;
    int network_code,weekend_status;
    printf("enter the mobile_load");
    scanf("%f",&mobile_load);
    if(mobile_load<100){
        printf("no bonus");
        return 1;
    }
    printf("enter the network code.where 1 = Jazz, 2 = Telenor, and 3 = Ufone\n");
    scanf("%d",&network_code);
    printf("enter weekend status : 1 = weekend and 0 = weekday");
    scanf("%d",&weekend_status);
    
     if (mobile_load>100||mobile_load<499){
        if(weekend_status==1 && network_code!=3){
            discount = mobile_load*0.10;
        }else{
            discount = mobile_load*0.05;
        }
    }else{
        discount = mobile_load*0.05;
    }
     if (mobile_load >= 500){
        if(weekend_status == 1 || network_code == 2){
            discount = mobile_load*0.20;
        }else{
           discount =  mobile_load*0.12;
        }
    }
    payable = mobile_load-discount;
    printf(" final amount %f",discount);
    printf(" final amount %f",payable);
     return 0;
}

# task 6

#include <stdio.h>

int main() {
int overdue_days, book_type, priority_membership;
    float fine,discount=0.0;
     printf("enteroverdue_days");
    scanf("%d",&overdue_days);
    printf("enter priority membership is 1 for yes and 0 for no");
    scanf("%d",&priority_membership);

    printf("enter booktype Book type 1 is Regular, 2 is Reference, and 3 is Rare");
    scanf("%d",&book_type);
if(book_type==1){
    if(overdue_days<=7){
        fine=overdue_days*5.0;
    }else{
        fine = (7*5.00)+((overdue_days-7)*10);
    }
}else if (book_type==2){
    fine = overdue_days*15;
}
    else if (book_type==3){
    fine = overdue_days*30;
}
    if (book_type == 3 && overdue_days > 10){
        printf("banned from borrwoing\n");
    }
    if (priority_membership==1 && book_type!=3){
    discount = overdue_days*0.80;
    }
    printf("%.2f fine is ",fine);
    return 0;
}

# task 7
#include <stdio.h>

int main() {
int matches_played,fitness_status;
    float batting;
    printf("enter match played");
    scanf("%d",&matches_played);
    if(matches_played<5){
        printf("Rejected — Insufficient Matches");
        return 1;
    }
   printf("enter and fitness failure status as an integer where 1 means failed and 0 means passed.");
    scanf("%d",&fitness_status);
    if (fitness_status==0){
        printf("Rejected — Fitness");
        return 1;
    }
    
    printf("enter batting average");
    scanf("%f",&batting);
    if(batting>=35 && matches_played>=10){
        printf("selected");
    }
    else if((batting>25 || batting <34.99) && ( matches_played>=20) ){
        printf("Selected (Experience Quota");
    } else {
        printf("Rejected — Fitness");
    }
    
    return 0;
}

# task 8 
#include <stdio.h>

int main() {
int meal_catagory, customer_type;
    float  service_rate,discount,final_amount,bill_amount,service_charge;
    printf("enter bill_amount");
    scanf("%f",&bill_amount);
    printf("enter meal catagory 1 = Fast Food, 2 = Desi Food, and 3 = Chinese");
    
    scanf("%d",&meal_catagory);
    printf("enter customer type 1 = Student and 2 = Regular.");
    scanf("%d",&customer_type);

    if (customer_type != 1 && customer_type != 2) {
        printf("Invalid Selection\n");
        return 0;
    }

    switch(meal_catagory){
        case 1 :
        service_rate = 0.05;
        break;
        case 2 : 
         service_rate = 0.08;
        break;
             case 3:
         service_rate = 0.10;
        break;
        default :
        printf("invalid selection");
         return 0;
    }
        if(bill_amount>=1000){
        if(customer_type==1){
            discount = bill_amount*0.15;
        }else{
            discount = bill_amount*0.10;
        }
    } else { // <-- FIXED: Removed the stray brace
        if (customer_type==1){
            discount = bill_amount*0.05;
        }else{
            discount = 0.0;
        }
    }

     service_charge = bill_amount * service_rate;
        final_amount = bill_amount + service_charge - discount;
    printf("%.2f\n",final_amount);
         printf("%.2f\n",discount);
        printf("%.2f\n",service_charge);
        
    return 0;
}
    return 0;
}
}
