# BMI_Calculator
from tkinter import *
import tkinter as tk
root = tk.Tk() #Initialize a tkinter GUI screen with dimensions 800 by 1000
root.title("BMI Calculator")
root.geometry("800x1000")
def submit(): #Accepts the text input provided by the user for height and weight (converted to ints) and computes the BMI. The BMI is then displayed on the GUI screen
    try:
        weight = int(entry.get())
        height = int(entryTwo.get())
        computeBMI = (weight / (height ** 2)) * 703
        displayLabel.config(text='Your computed BMI is: {:.2f}'.format(computeBMI))
    except ValueError: #If values are entered incorrectly, a valueError is passed by the program
        displayLabel.config(text='Please enter valid numbers for weight and height.')
def submitHeight():
    pass
labelTitle = tk.Label(root, text='BMI Calculator', font=('Arial', 20, 'bold')) #Prints the 1st label onto the GUI at the top center of screen
labelTitle.place(x=100, y=0)

instructionLabel = tk.Label(root, text='Enter your weight in pounds and your height in inches to compute your BMI', font=('Arial', 15)) #Prints the label onto the screen that provides instructions to the user
instructionLabel.place(x=0, y=40)

weightTitle = tk.Label(root, text='Enter weight in pounds below: ', font=('Arial', 15)) #Prompts the user to provide their weight
weightTitle.place(x=0, y=80)

entry = Entry(root, font=('Arial', 20)) #User can enter their weight into this textbox which is passed over to the submit function in the next section of code
entry.place(x=0, y=120)

submitButton = Button(root, text='submit weight', command=submit)
submitButton.place(x=300, y=120)

heightTitle = tk.Label(root, text='Enter your height only in inches: ', font=('Arial', 15)) #Prompt for height, gets passed into submitHeight() which itself gets passed into submit() to calculate BMI
heightTitle.place(x=0, y=160)

entryTwo = Entry(root, font=('Arial', 20))
entryTwo.place(x=0, y=200)

otherButton = Button(root, text='submit height', command=submitHeight) #Submit height button
otherButton.place(x=300, y=200)

displayLabel = tk.Label(root, text='', font=('Arial', 15))
displayLabel.place(x=0, y=240)

BMIInfo = tk.Label(root, text='Your BMI is a measure of your body fat based on height and weight.', font=('Arial',15)) #Provides general information on BMI for users
BMIInfo.place(x=0,y=280)

info = tk.Label(root, text="Healthy BMI's are between 18 and 25, anything above is obese and anything below is underweight", font=('Arial',15))
info.place(x=0, y=320)

root.mainloop() #runs the event loop code and makes sure the buttons, labels, and text-boxes work
