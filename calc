
package com.mycompany.waelnew;

import java.util.Scanner;

public class calcnew {
    static float evaluator(String []stringFixed){
        
        
        float []answersOnly=new float[stringFixed.length];
        int currentIndex=0;
        System.out.println();
        for( int z=0;z<stringFixed.length;z++){
            if(stringFixed[z].equals("*")||stringFixed[z].equals("/")||stringFixed[z].equals("-")||stringFixed[z].equals("+")){
              switch(stringFixed[z]){
                case"*":
                     float numLeft=answersOnly[currentIndex-2]; 
                     float numRight=answersOnly[currentIndex-1];
                     answersOnly[currentIndex-2]=numLeft*numRight;
                     currentIndex-=1;
                     break;
                case"/":
                     float numLeft1=answersOnly[currentIndex-2]; 
                     float numRight1=answersOnly[currentIndex-1];
                     answersOnly[currentIndex-2]=numLeft1/numRight1;
                     currentIndex-=1;
                     break;
                 case"-":
                     float numLeft2=answersOnly[currentIndex-2]; 
                     float numRight2=answersOnly[currentIndex-1];
                     answersOnly[currentIndex-2]=numLeft2-numRight2;
                     currentIndex-=1;
                     break;
                case"+":
                     float numLeft3=answersOnly[currentIndex-2]; 
                     float numRight3=answersOnly[currentIndex-1];
                     answersOnly[currentIndex-2]=numLeft3+numRight3;
                     currentIndex-=1;
                     break;
              }
            } 
            else{
                answersOnly[currentIndex]=Integer.parseInt(String.valueOf(stringFixed[z]));
                currentIndex+=1;}
            }
     return answersOnly[0];
    }          
    static String[] postfix(String phrase){
        Character drb = '*';
        Character ksm = '/';
        Character jme = '+';
        Character ngs = '-';
        char arraySimplified[]=new char[phrase.length()];
        String arrayNumbers[]=new String[arraySimplified.length];
        char arrayOp[]=new char[arraySimplified.length];
        int countNum=0;
        boolean previousNum=false;
        int countOp=0;
        for(int i=0;i<phrase.length();i++){
            arraySimplified[i]=phrase.charAt(i);
        }    
        for(int s=0;s<arraySimplified.length;s++){//5+2/4-3*2 
            if (Character.isDigit(arraySimplified[s])){
                if (previousNum){
                    if (countNum>0)
                     arrayNumbers[countNum-1]+=String.valueOf(arraySimplified[s]);
                }
                else if(previousNum==false){    
                arrayNumbers[countNum]=String.valueOf(arraySimplified[s]);
                    countNum+=1;           
                    previousNum=true;}
            }
          else if(arraySimplified[s]==drb ||arraySimplified[s]==ksm ||arraySimplified[s]==jme ||arraySimplified[s]==ngs){
              previousNum=false; 
              if(countOp>=arraySimplified.length){
                break;}
                arrayOp[countOp]=arraySimplified[s];
                if(countOp==1){ 
                if((arrayOp[countOp]==ngs||arrayOp[countOp]==jme)&&(arrayOp[countOp-1]==ksm||arrayOp[countOp-1]==drb)){
                    arrayNumbers[countNum]=String.valueOf(arrayOp[countOp-1]); //   + / -
                    arrayOp[countOp-1]=arrayOp[countOp];//     + -
                    countNum+=1;
                    countOp-=1;
                    }
                else if((arrayOp[countOp]==ngs||arrayOp[countOp]==jme)&&(arrayOp[countOp-1]==ngs||arrayOp[countOp-1]==jme)){
                    arrayNumbers[countNum]=String.valueOf(arrayOp[countOp-1]);
                    arrayOp[countOp-1]=arrayOp[countOp];
                    countNum+=1;
                    countOp-=1;
                }
                else if((arrayOp[countOp]==drb||arrayOp[countOp]==ksm)&&(arrayOp[countOp-1]==drb||arrayOp[countOp-1]==ksm)){
                    arrayNumbers[countNum]=String.valueOf(arrayOp[countOp-1]);
                    arrayOp[countOp-1]=arrayOp[countOp];
                    countNum+=1;
                    countOp-=1;
                }
                }
                else if(countOp>1){ 
                if((arrayOp[countOp]==ngs||arrayOp[countOp]==jme)&&(arrayOp[countOp-1]==ksm||arrayOp[countOp-1]==drb)){
                    arrayNumbers[countNum]=String.valueOf(arrayOp[countOp-1]); //   + / -
                    arrayOp[countOp-1]=arrayOp[countOp];//     + -
                    countNum+=1;
                    countOp-=1;
                    if ((arrayOp[countOp]==ngs||arrayOp[countOp]==jme)&&(arrayOp[countOp-1]==ngs||arrayOp[countOp-1]==jme)){
                        arrayNumbers[countNum]=String.valueOf(arrayOp[countOp-1]);
                        arrayOp[countOp-1]=arrayOp[countOp];
                        countNum+=1;
                        countOp-=1;
                    
                    }
                }
                else if((arrayOp[countOp]==ngs||arrayOp[countOp]==jme)&&(arrayOp[countOp-1]==ngs||arrayOp[countOp-1]==jme)){
                    arrayNumbers[countNum]=String.valueOf(arrayOp[countOp-1]);
                    arrayOp[countOp-1]=arrayOp[countOp];
                    countNum+=1;
                    countOp-=1;
                }
                else if((arrayOp[countOp]==drb||arrayOp[countOp]==ksm)&&(arrayOp[countOp-1]==drb||arrayOp[countOp-1]==ksm)){
                    arrayNumbers[countNum]=String.valueOf(arrayOp[countOp-1]);
                    arrayOp[countOp-1]=arrayOp[countOp];
                    countNum+=1;
                    countOp-=1;
                }
                }
                    countOp+=1;}
        }
       countOp-=1;
       while(countOp>=0){
           if (countOp>=0){    
                arrayNumbers[countNum]=String.valueOf(arrayOp[countOp]);
                countOp-=1;
                countNum+=1;  }
       }//

        int newlength=0;
        for(String i:arrayNumbers){
            
            if (i==null)
                continue;
            else
                newlength+=1;
        }
        String arrayNumbersNulls[]=new String[newlength];
        for(int i=0;i<newlength;i++){
            arrayNumbersNulls[i]=arrayNumbers[i];
        
        }
       // System.out.println("final" + countOp);
         return arrayNumbersNulls;
    }
    public static void main(String args[]){
    
    Scanner input=new Scanner(System.in);
        System.out.println("Enter Math Phrase: ");
        String mathPhrase=input.next();
        String wholePhrase=input.nextLine();
        mathPhrase+=wholePhrase;
        String clean=mathPhrase.replace(" ", "");
       
        
       System.out.println(evaluator(postfix(clean)));
        
    }
}

