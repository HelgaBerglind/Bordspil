# Bordspil
bordspil verkefni
Höfundar: Súsanna, Þórhallur, Helga

Tilgangurinn með spilinu er að komast fyrst á endareitinn.

til að byrja spilið þurfa allir að ýta á takkan á miðju borðinu.
sá sem fær lægstu töluna byrjar.

Kóðinn:

from machine import Pin, PWM
from random import randint
from time import sleep_ms
from utime import sleep
buzzer = PWM(Pin(21))

tones = {
"B0": 31,"C1": 33,"CS1": 35,"D1": 37,"DS1": 39,"E1": 41,"F1": 44,"FS1": 46,
"G1": 49,"GS1": 52,"A1": 55,"AS1": 58,"B1": 62,"C2": 65,
"CS2": 69,"D2": 73,"DS2": 78,"E2": 82,"F2": 87,"FS2": 93,"G2": 98,
"GS2": 104,"A2": 110,"AS2": 117,"B2": 123,"C3": 131,"CS3": 139,
"D3": 147,"DS3": 156,"E3": 165,"F3": 175,"FS3": 185,
"G3": 196,"GS3": 208,"A3": 220,"AS3": 233,"B3": 247,"C4": 262,"CS4": 277,"D4": 294,"DS4": 311,
"E4": 330,"F4": 349,"FS4": 370,"G4": 392,"GS4": 415,"A4": 440,"AS4": 466,"B4": 494,"C5": 523,"CS5": 554,"D5": 587,"DS5": 622,"E5": 659,"F5": 698,
"FS5": 740,"G5": 784,"GS5": 831,"A5": 880,"AS5": 932,"B5": 988,"C6": 1047,"CS6": 1109,"D6": 1175,"DS6": 1245,"E6": 1319,"F6": 1397,"FS6": 1480,"G6": 1568,"GS6": 1661,
"A6": 1760,"AS6": 1865,"B6": 1976,"C7": 2093,"CS7": 2217,"D7": 2349,"DS7": 2489,"E7": 2637,"F7": 2794,"FS7": 2960,"G7": 3136,"GS7": 3322,"A7": 3520,
"AS7": 3729,"B7": 3951,"C8": 4186,"CS8": 4435,"D8": 4699,"DS8": 4978
}

tetris = ["E5", "E5", 0, 0, "B4", "B4", "C5", "C5", "D5", "D5", 0, 0, "C5", "C5", "B4", "B4", "A4", "A4", 0, 0, "A4", "A4", "C5", "C5", "E5", "E5", 0, 0, "D5", "D5", "C5", "C5", "B4", "B4", 0, 0, 0, 0,"C5", "C5", "D5", "D5", 0, 0, "E5", "E5", 0, 0, "C5", "C5", 0, 0, "A4", "A4", 0, 0, "A4", "A4"]

sigurlag = ["B4", 0, "B4", 0, "B4", 0, "B4", "B4", "B4", "B4", 0, "G4", "G4", "G4", "G4", 0, "A4", "A4", "A4", "A4", 0, "B4", "B4", "B4", 0, "A4", 0, "B4", "B4", "B4", "B4", "B4", "B4"]

def playtone(frequency):
    buzzer.duty_u16(1000)
    buzzer.freq(frequency)

def bequiet():
    buzzer.duty_u16(0)

def playsong(mysong):
    for i in range(len(mysong)):
        if (mysong[i] == 0 ):
            bequiet()
        else:
            playtone(tones[mysong[i]])
        sleep(0.07)
    bequiet()
playsong(tetris)

led1 = Pin(2, Pin.OUT)
led2 = Pin(16, Pin.OUT)
led3 = Pin(17, Pin.OUT)
led4 = Pin(18, Pin.OUT)
led5 = Pin(10, Pin.OUT)
led6 = Pin(11, Pin.OUT)
led7 = Pin(12, Pin.OUT)
led8 = Pin(13, Pin.OUT)
takki = Pin(14, Pin.IN, Pin.PULL_UP)
reed = Pin(7, Pin.IN, Pin.PULL_UP)

pins = [led1, led2, led3, led4, led5, led6, led7, led8]

while True:  
    if not takki.value():
        led1.value(1)
        sleep_ms(15)
        led1.value(0)
        led2.value(1)
        sleep_ms(30)
        led2.value(0)
        led3.value(1)
        sleep_ms(45)
        led3.value(0)
        led4.value(1)
        sleep_ms(60)
        led4.value(0)
        led5.value(1)
        sleep_ms(75)
        led5.value(0)
        led6.value(1)
        sleep_ms(90)
        led6.value(0)
        led7.value(1)
        sleep_ms(105)
        led7.value(0)
        led8.value(1)
        sleep_ms(120)
        led8.value(0)
        led1.value(1)
        sleep_ms(135)
        led1.value(0)
        led2.value(1)
        sleep_ms(150)
        led2.value(0)
        led3.value(1)
        sleep_ms(165)
        led3.value(0)
        led4.value(1)
        sleep_ms(180)
        led4.value(0)
        led5.value(1)
        sleep_ms(195)
        led5.value(0)
        led6.value(1)
        sleep_ms(210)
        led6.value(0)
        led7.value(1)
        sleep_ms(225)
        led7.value(0)
        led8.value(1)
        sleep_ms(240)
        led8.value(0)
        led1.value(1)
        sleep_ms(255)
        led1.value(0)
        led2.value(1)
        sleep_ms(270)
        led2.value(0)
        led3.value(1)
        sleep_ms(285)
        led3.value(0)
        led4.value(1)
        sleep_ms(300)
        led4.value(0)
        led5.value(1)
        sleep_ms(315)
        led5.value(0)
        led6.value(1)
        sleep_ms(330)
        led6.value(0)
        led7.value(1)
        sleep_ms(345)
        led7.value(0)
        led8.value(1)
        sleep_ms(360)
        led8.value(0)
        randomLed = randint(0, 7)
        print(randomLed)
        pins[randomLed].value(1)
        sleep_ms(2000)
        led1.value(0)
        led2.value(0)
        led3.value(0)
        led4.value(0)
        led5.value(0)
        led6.value(0)
        led7.value(0)
        led8.value(0)
       
    if not reed.value():
        playsong(sigurlag)
