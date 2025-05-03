def integ(value):
    value = float(value)
    if value.is_integer():
        return int(value) 
    else:
        return round(value, 2) 

def seconder(n, f, t):
    factors = {
        'second' : {'minute': 1/60, 'hour': 1/3600, 'day': 1/86400, 'month': 1/2629746, 'year': 1/31556952},
        'minute' : {'second': 60, 'hour': 1/60, 'day': 1/1440, 'month': 1/43829.1, 'year': 1/525949.2},
        'hour' : {'minute': 60, 'second': 3600, 'day': 1/24, 'month': 1/730.484, 'year': 1/8765.82},
        'day' : {'minute': 24, 'hour': 1440, 'second': 86400, 'month': 1/30.44, 'year': 1/365.2425},
        'month' : {'minute': 43829.1, 'hour': 730.484, 'day': 30.4375, 'second': 2629746, 'year': 1/12},
        'year' : {'minute': 525949.2, 'hour': 8765.81, 'day': 365.2425, 'month': 12, 'second': 31556952}
        }
    return integ(n * factors[f.lower()][t.lower()])

def distancer(n, f, t):
    factors = {
        'meter': {'mile': 1/1609, 'yard': 1.094, 'foot': 3.281, 'inch': 39.37},
        'mile': {'meter': 1609, 'yard': 1760, 'foot': 5280, 'inch': 63360},
        'yard': {'meter': 1/1.094, 'mile': 1/1760, 'foot': 3, 'inch': 36},
        'foot': {'meter': 1/3.281, 'mile': 1/5280, 'yard': 1/3, 'inch': 12},
        'inch': {'meter': 1/39.37, 'mile': 1/63360, 'yard': 1/36, 'foot': 1/12}
    }
    return integ(n * factors[f.lower()][t.lower()])

def currenter(t):
    t = t.lower()
    prompts = {
        "ampere": ["watts", "volts"],
        "volt": ["watts", "amperes"],
        "watt": ["volts", "amperes"],
        "ohm": ["volts", "amperes"],
        "coloumb": ["seconds", "amperes"],
        "joule": ["seconds", "watts"]
    }
    ops = {
        "ampere": lambda w, v: w / v,
        "volt": lambda w, a: w / a,
        "watt": lambda v, a: v * a,
        "ohm": lambda v, a: v / a,
        "coloumb": lambda s, a: s * a,
        "joule": lambda s, w: s * w
    }
    values = [integ(input(f"Give Amount Of {x.capitalize()}: ")) for x in prompts[t]]
    return integ(ops[t](*values))

def weighter(n, f, t):
    factors = {
        'kilogram': {'pound': 2.205, 'tonne': 1/1000, 'ton': 1/907.2, 'newton': 9.81},
        'pound': {'kilogram': 1/2.205, 'tonne': 1/2205, 'ton': 1/2000, 'newton': 4.448},
        'tonne': {'pound': 2205, 'kilogram': 1000, 'ton': 1.102, 'newton': 1000*9.81},
        'ton': {'pound': 2000, 'kilogram': 907.2, 'tonne': 1/1.102, 'newton': 8896.44},
        'newton': {'pound': 1/4.448, 'tonne': 1/1000/9.81, 'ton': 1/8896.44, 'kilogram': 1/9.81}
    }
    return integ(n * factors[f.lower()][t.lower()])

def heater(n, f, t):
    f, t = f.lower(), t.lower()
    conversions = {
        ('kelvin', 'celsius'): lambda x: x - 273.15,
        ('kelvin', 'fahrenheit'): lambda x: (x - 273.15) * 9/5 + 32,
        ('kelvin', 'rankine'): lambda x: x * 1.8,
        ('celsius', 'kelvin'): lambda x: x + 273.15,
        ('celsius', 'fahrenheit'): lambda x: (x * 9/5) + 32,
        ('celsius', 'rankine'): lambda x: x * 1.8 + 491.67,
        ('fahrenheit', 'kelvin'): lambda x: (x - 32) * 5/9 + 273.15,
        ('fahrenheit', 'celsius'): lambda x: (x - 32) * 5/9,
        ('fahrenheit', 'rankine'): lambda x: x + 459.67,
        ('rankine', 'kelvin'): lambda x: x * 5/9,
        ('rankine', 'celsius'): lambda x: (x - 491.67) * 5/9,
        ('rankine', 'fahrenheit'): lambda x: x - 459.67,
    }
    return integ(conversions[(f, t)](n))

def moler(t):
    t = t.lower()
    operations = {
        "mole": lambda l, c: l * c,
        "liter": lambda m, c: m / c,
        "concentration": lambda m, l: m / l
    }
    prompts = {
        "mole": ["Liters", "Concentration"],
        "liter": ["Moles", "Concentration"],
        "concentration": ["Moles", "Liters"]
    }
    values = [integ(input(f"Give Amount Of {x.capitalize()}: ")) for x in prompts[t]]
    return integ(operations[t](*values))

def lighter(t):
    t = t.lower()
    operations = {
        "candela": lambda l, s: l / s,
        "lumen": lambda c, s: c * s,
        "steradian": lambda l, c: l / c,
        "lux": lambda l, a: l / a
    }
    prompts = {
        "candela": ["Lumens", "Steradians"],
        "lumen": ["Candelas", "Steradians"],
        "steradian": ["Lumens", "Candelas"],
        "lux": ["Lumens", "Square Meters"]
    }
    values = [integ(input(f"Give Amount Of {x.capitalize()}: ")) for x in prompts[t]]
    return integ(operations[t](*values))

print("\nWelcome to the Rushi's Unit Converter!")
print("Choose a category from the list below:\n")
print("1. Time")
print("2. Distance")
print("3. Electric Current / Power")
print("4. Weight")
print("5. Temperature")
print("6. Substance")
print("7. Light Intensity\n")

while True:
    c = input("Enter the S. No. of the category (1-7): ")
    try:
        c = int(c)
        if 1 <= c <= 7:
            break
        else:
            print("⚠️ Please enter a number between 1 and 7.")
    except ValueError:
        print("⚠️ Invalid input. Please enter a number.")

categories = {
    1: ("Time", seconder),
    2: ("Distance", distancer),
    3: ("Electricity", currenter),
    4: ("Weight", weighter),
    5: ("Temperature", heater),
    6: ("Substance", moler),
    7: ("Light", lighter)
}

lister = {
    1 : {1: "second", 2: "minute", 3: "hour", 4: "day", 5: "month", 6: "year"},
    2 : {1: "meter", 2: "mile", 3: "yard", 4: "foot", 5: "inch"},
    3 : {1: "ampere", 2: "volt", 3: "watt", 4: "ohm", 5: "coloumb", 6: "joule"},
    4 : {1: "kilogram", 2: "pound", 3: "ton", 4: "tonne", 5: "newton"},
    5 : {1: "kelvin", 2: "celsius", 3: "fahrenheit", 4: "rankine"},
    6 : {1: "mole", 2: "liter", 3: "concentration"},
    7 : {1: "candela", 2: "lumen", 3: "steradian", 4: "lux"}
}

name, func = categories[c]
print(f"\nYou Chose Category: {name}")

if c in [1, 2, 4, 5]:
    for sno, unit in lister[c].items():
        print(f"{sno}. {unit}")
    while True:
        try:
            fc = True
            while fc:
                try:
                    f = int(input("\nConvert from unit (S. No.): "))
                    f = int(f)
                    if 1 <= f <= len(lister[c]):
                        f = lister[c][f]
                        fc = False
                    else:
                        print(f"⚠️ Invalid input. Please enter a number between 1-{len(lister[c])}.\n")
                except (ValueError, KeyError):
                    print("⚠ Invalid inputs or units for this calculation.\n")
            tc = True
            while tc:
                try:
                    t = int(input("\nConvert to unit (S. No.): "))
                    t = int(t)
                    if 1 <= t <= len(lister[c]):
                        t = lister[c][t]
                        tc = False
                    else:
                        print(f"⚠️ Invalid input. Please enter a number between 1-{len(lister[c])}.\n")
                except (ValueError, KeyError):
                    print("⚠ Invalid inputs or units for this calculation.\n")
            n = float(input("Enter the value to convert: "))
            result = func(n, f, t)
            print(f"\nResult: {result} {t.capitalize()}{'s' if result != 1 else ''}")
            break
        except (ValueError, KeyError):
            print("⚠ Invalid input. Please use valid numbers.\n")

elif c in [3, 6, 7]:
    for sno, unit in lister[c].items():
        print(f"{sno}. {unit}")
    while True:
        t = input("\nWhat do you want to calculate? (S. No.): ")
        try:
            t = int(t)
            if 1 <= t <= len(lister[c]):
                t = lister[c][t]
                result = func(t)
                print(f"\nResult: {result} {t.capitalize()}{'s' if result != 1 else ''}")
                break
            else:
                print(f"⚠️ Invalid input. Please enter a number between 1-{len(lister[c])}.")
        except (KeyError, ZeroDivisionError, ValueError):
            print("⚠ Invalid inputs or units for this calculation.")
