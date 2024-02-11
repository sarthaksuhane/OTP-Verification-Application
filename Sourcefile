from tkinter import *
from twilio.rest import Client
import random
from tkinter import messagebox

class otp_verifier(Tk):
    def __init__(self):
        super().__init__()
        self.geometry("1000x580+200+80")
        self.configure(bg = "#FFFFFF")
        self.resizable(False, False)
        self.n = str(self.OTP())
        self.client = Client("ACefd1e77912f0845823618f4e3f717342", "5b3e4b6a1a4b3e945e57ab4d508efb20")
        self.client.messages.create(to=("+918770775012"),
                                    from_="+14788181436",
                                    body= self.n)

    def Labels(self):
        self.c = Canvas(self, bg = "#0086b3", width=400, height=280)
        self.c.place(x = 290, y = 120)

        self.upper_frame = Frame(self, bg = "#006699", width = 1500, height = 130)
        self.upper_frame.place(x=0, y=0)

        self.picture = PhotoImage(file = "password1.png")
        self.k = Label(self.upper_frame, image = self.picture, bg = "#006699").place(x = 220, y = 35)

        self.j = Label(self.upper_frame, text = "Verify OTP", font = "Verdana 38 bold", bg = '#006699', fg = "white").place(x = 370, y = 35)

    def Entry(self):
        self.User_Name = Text(self, font = "calibri 20", borderwidth=2, wrap = WORD, width = 23, height = 1)
        self.User_Name.place(x = 330, y = 200)

    def OTP(self):
        return random. randrange(1000, 10000)

    def Buttons(self):
        self.submitButtonImage = PhotoImage(file = "submit.png")
        self.submitButton = Button(self, image = self.submitButtonImage, command = self.checkOTP, border = 0)
        self.submitButton.place(x = 440, y = 330)

        self.resendOTPImage = PhotoImage(file = "resendotp.png")
        self.resendOTP = Button(self, image = self.resendOTPImage, command = self.resendOTP, border = 0)
        self.resendOTP.place(x = 420, y = 430)

    def resendOTP(self):
        self.n = str(self.OTP())
        self.client = Client("ACefd1e77912f0845823618f4e3f717342", "5b3e4b6a1a4b3e945e57ab4d508efb20")
        self.client.messages.create(to=("+918770775012"),
                                    from_="+14788181436",
                                    body= self.n)                                   
        
    def checkOTP(self):
        try:
            self.userInput = int(self.User_Name.get(1.0, "end -1c"))
            if self.userInput == int(self.n):
                messagebox.showinfo("showinfo", "Verfication Successful")
                self.n = "done"
            else:
                messagebox.showinfo("showinfo", "Wrong OTP")
        except:
            messagebox.showinfo("showinfo", "INVALID OTP")

if __name__ == "__main__":
    window = otp_verifier()
    window.Labels()
    window.Entry()
    window.OTP()
    window.Buttons()
    window.mainloop()
