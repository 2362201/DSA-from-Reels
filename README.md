# DSA-from-Reels

# 🧠 Reel Reasoner – Solve Reels Like a Coder

A unique project that converts viral reels (like “Who is dead?” or “Who stole the diamond?”) into structured DSA logic (Trees, DP, Graphs, etc.) using a custom DSL (Domain-Specific Language) parser.

## 🔧 Technologies
- C++ / Python
- Custom DSA Engine

## 🧠 Example
> Scene: “Who stole the diamond?”
> B is holding a glove, A has hands hidden, C is scared.
> DSL logic applies tree traversal → Result: B is thief.

## 👀 Output
- 🔹 DSA Explanation
- 🔹 DSA Mapping
- 🔹 Code & Logical Steps
## CODE:-



#include<iostream>
#include<unordered_map>
#include<string>
using namespace std;

struct Person{
    char id;
    bool isFloat;
    bool isMove;
    bool isEyeOpen;
    bool isHoldObject;
};
unordered_map<char, bool>mp;

bool isDead(Person p){
    if(mp.find(p.id)!=mp.end()) return mp[p.id];

    if(p.isFloat && !p.isMove && p.isEyeOpen && !p.isHoldObject){
        return mp[p.id] = true;
    }
    return mp[p.id] = false;
};

int main(){

    Person A  = {'A', true, false, true, false}; // Dead
    Person B  = {'B', false, true, true, false}; // Alive
    Person C  = {'C', true, true, false, true}; // Alive
    if(isDead(A)) {
        cout<<"Person A is dead"<<endl;
    }
    else if(isDead(B)){
        cout<<"Person B is dead"<<endl;
    }
    else if(isDead(C)){
        cout<<"Person C is dead"<<endl;
    }
    else{
        cout<<"All are alive"<<endl;
    }

    cout<<"Memo Table:\n";
    for(auto pair : mp){
        cout<<"Person"<<pair.first<<":"<<(pair.second ? "Dead" : "Alive")<<endl;
    }
    return 0;
}
