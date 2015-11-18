using UnityEngine;
using System.Collections;

public class NumberWizard : MonoBehaviour {
    int max;
    int min;
    int guess;
    // Use this for initialization
    void Start () {
        StartGame();
	}
    void StartGame()
    {
        max = 1000;
        min = 1;
        guess = 500;

        max = max + 1;

        print("=============================================");
        print("Welcome to Number Guesser");
        print("Pick a number from 1-1000");


        print("Is the number higher or lower than " + guess);
        print("Up arrow for higher, down for lower, return for equal");
    }
   
    // Update is called once per frame
    void Update() {
        if (Input.GetKeyDown(KeyCode.UpArrow))
        {
           
            min = guess;
            NextGuess();
        }
        else if (Input.GetKeyDown(KeyCode.DownArrow))
        {
            max = guess;
            guess = (max + min) / 2;
            print("Higher or lower than " + guess);
            print("Up arrow for higher, down for lower, return for equal");
        }
        else if (Input.GetKeyDown(KeyCode.Return))
        {
            print("I Win");
            StartGame();
        }

        }
    void NextGuess()
    {
        guess = (max + min) / 2;
        print("Higher or lower than " + guess);
        print("Up arrow for higher, down for lower, return for equal");
    }
}
