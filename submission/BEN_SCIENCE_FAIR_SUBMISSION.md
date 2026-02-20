# Ben's Science Fair — Assignment #5/6/7
# Due: Friday, February 20, 2026
# Ben Massfeller, Grade 5, Ms. Sofferin

---

## TITLE

**Does Adding Weight to a Hot Wheels Car Make It Go Faster or Slower?**

---

## ABSTRACT

I wanted to find out if making a Hot Wheels car heavier would make it go faster or slower down a ramp. I used two Ford F-150 Hot Wheels trucks and tested them on a 5.85-meter track. I added tungsten weights to the cars — first 3.5 grams, then 7 grams, then 14 grams — and ran each one 3 times. My dad and I built a speed trap called the M.A.S.S. Trap that uses sensors to time each run.

I found out that adding a little bit of weight made both cars faster, but adding a lot of weight (14g) made the heavier car slower. The lighter car kept getting faster the whole time. So weight does matter, but it depends on how heavy the car already is.

I also taped a tiny computer with a motion sensor to a VW Truck to see what the car feels during a run. It recorded forces up to 4 times gravity and even caught a crash where the car was spinning at 339 RPM!

---

## TESTABLE QUESTION

Does adding weight to a Hot Wheels car change how fast it goes down a 5.85-meter ramp?

---

## HYPOTHESIS

If I add more weight to a Hot Wheels car, then it will go faster down the ramp, because heavier things have more energy at the top of the ramp.

---

## VARIABLES

- **Independent Variable (what I changed):** How much weight I added — 0g, 3.5g, 7g, or 14g of tungsten
- **Dependent Variable (what I measured):** Speed (meters per second) and time (seconds)
- **Controlled Variables (what I kept the same):** Track length (5.85m), where I put the car at the top, how I let go, the type of car (F-150 truck), and the NFC sticker weight (0.025g each)

---

## MATERIALS

1. M.A.S.S. Trap speed trap system (built by me and my dad using an ESP32 computer and infrared sensors)
2. Hot Wheels track — 5.85 meters long
3. 2 Hot Wheels Ford F-150 trucks (same model, from the same package)
   - "F-150 Control" — 38.025 grams (the heavier one)
   - "F-150 Test" — 31.546 grams (the lighter one)
4. 1 Hot Wheels VW Truck — 34.626 grams (for the sensor ride-along test)
5. Tungsten weights — 3.5g, 7g, and 14g pieces
6. Digital scale that measures to 0.001 grams
7. 2 NFC stickers to identify each car (0.025g each)
8. Laptop to see the M.A.S.S. Trap dashboard
9. XIAO ESP32-S3 mini computer with a motion sensor (13.8g total, taped to the car roof)
10. Small battery for the XIAO sensor

---

## PROCEDURE

1. Weigh each car on the scale and write down the weight.
2. Put an NFC sticker on each car. Weigh again and write down the new weight.
3. Set up the track with sensors at the start and finish.
4. Open the M.A.S.S. Trap dashboard on my laptop.
5. **No added weight:** Put the car at the top of the ramp. Let go. The sensors time it automatically. Do this 3 times for each car, switching back and forth (Control, Test, Control, Test...).
6. **+3.5g:** Tape 3.5 grams of tungsten to each car. Run 3 trials per car.
7. **+7g:** Tape 7 grams of tungsten to each car. Run 3 trials per car.
8. **+14g:** Tape 14 grams of tungsten to each car. Run 3 trials per car.
9. The system saves everything automatically — time, speed, momentum, and kinetic energy.
10. Look at the data and figure out the averages.

---

## DATA

### F-150 Control Car (starts at 38.025g)

| Condition | Total Weight (g) | Trial 1 (s) | Trial 2 (s) | Trial 3 (s) | Avg Time (s) | Avg Speed (m/s) |
|-----------|-----------------|-------------|-------------|-------------|--------------|----------------|
| No weight added | 38.025 | 1.561 | 1.507 | 1.490 | 1.519 | 3.85 |
| +3.5g tungsten | 41.525 | 1.481 | 1.481 | 1.515 | 1.492 | 3.92 |
| +7g tungsten | 45.025 | 1.504 | 1.478 | 1.499 | 1.493 | 3.92 |
| +14g tungsten | 52.025 | 1.515 | 1.508 | 1.483 | 1.502 | 3.90 |

> One run with +14g was really slow (1.687s). I think the car hit the wall. I did an extra run to replace it.

### F-150 Test Car (starts at 31.546g)

| Condition | Total Weight (g) | Trial 1 (s) | Trial 2 (s) | Trial 3 (s) | Avg Time (s) | Avg Speed (m/s) |
|-----------|-----------------|-------------|-------------|-------------|--------------|----------------|
| No weight added | 31.546 | 1.544 | 1.510 | 1.477 | 1.510 | 3.88 |
| +3.5g tungsten | 35.046 | 1.474 | 1.480 | 1.518 | 1.491 | 3.93 |
| +7g tungsten | 38.546 | 1.512 | 1.470 | 1.515 | 1.499 | 3.91 |
| +14g tungsten | 45.546 | 1.468 | 1.481 | 1.473 | 1.474 | 3.97 |

### Physics Math (using the averages)

I also calculated momentum and kinetic energy for each condition:
- **Momentum** = mass × speed (how hard something hits)
- **Kinetic energy** = ½ × mass × speed² (how much energy something has while moving)

| Condition | Car | Mass (kg) | Speed (m/s) | Momentum (kg·m/s) | Kinetic Energy (J) |
|-----------|-----|-----------|-------------|--------------------|--------------------|
| No weight | Control | 0.038 | 3.85 | 0.147 | 0.282 |
| No weight | Test | 0.032 | 3.88 | 0.122 | 0.237 |
| +3.5g | Control | 0.042 | 3.92 | 0.163 | 0.319 |
| +3.5g | Test | 0.035 | 3.93 | 0.138 | 0.270 |
| +7g | Control | 0.045 | 3.92 | 0.176 | 0.346 |
| +7g | Test | 0.039 | 3.91 | 0.151 | 0.294 |
| +14g | Control | 0.052 | 3.90 | 0.197 | 0.374 |
| +14g | Test | 0.046 | 3.97 | 0.181 | 0.359 |

### Bonus: VW Truck with a Ride-Along Sensor

I also taped a tiny computer (called a XIAO) with a motion sensor to a VW Truck to see what the car actually feels during a run. The sensor took 100 readings per second.

**Runs with the sensor taped on (VW Truck M41, 48.5g total):**

| Run | Time (s) | Speed (m/s) |
|-----|----------|-------------|
| 7 | 1.522 | 3.85 |
| 8 | 1.459 | 4.01 |
| 10 | 1.505 | 3.89 |
| 11 | 1.496 | 3.91 |
| **Average** | **1.495** | **3.91** |

**Runs without the sensor (same truck, 48.884g with just tape):**

| Run | Time (s) | Speed (m/s) |
|-----|----------|-------------|
| 13 | 1.447 | 4.04 |
| 14 | 1.465 | 3.99 |
| **Average** | **1.456** | **4.02** |

The truck without the sensor on the roof was actually faster, even though it weighed a tiny bit more! That's because the sensor on the roof made the car top-heavy and wobbly.

**What the sensor recorded on a normal run:**
- The car feels a strong push when it starts (about 1.5 times gravity)
- It rolls for about 640 milliseconds (less than 1 second)
- It wobbles a little but stays on its wheels
- After it crosses the finish line, it slows down and stops right-side-up

**What the sensor recorded during a crash:**
- The car started spinning immediately — 289 RPM at the very first reading!
- It tumbled for almost a whole second before hitting the ground
- The biggest force was 4.06g — that's 4 times gravity
- It was spinning at 339 RPM at the worst point (faster than a blender on low!)
- The car landed on its left side
- The crash broke the battery loose and damaged the sensor

> I got 3 of the 5 runs back from the sensor's memory. The other 2 were erased by the sensor automatically to make room. My dad and I had to read 1.5 million bytes of raw memory from the chip to find the data.

---

## RESULTS

**Both cars got faster when I added a little bit of weight.**
- The Control car went from 3.85 m/s to 3.92 m/s with +3.5g. That's a little bit faster.
- The Test car went from 3.88 m/s to 3.93 m/s with +3.5g. Also a little faster.

**But the two cars did different things when I added a lot of weight (+14g).**
- The Control car (the heavier one) got **slower** — it went back down to 3.90 m/s. Too much weight!
- The Test car (the lighter one) kept getting **faster** — it hit 3.97 m/s, the fastest run of any car!

**Momentum went up every time I added weight.** That makes sense because momentum = mass × speed. Even when speed stayed about the same, more mass means more momentum.

**Kinetic energy also went up every time.** KE = ½ × mass × speed². More mass = more energy, even if the car isn't going much faster.

### Patterns I Found

1. **There's a sweet spot.** Adding 3.5g was the best amount for both cars. It made them faster without slowing them down.
2. **More isn't always better.** For the Control car, adding more than 3.5g didn't really help, and 14g actually made it slower.
3. **Lighter cars can handle more weight.** The Test car kept getting faster all the way to +14g because it started lighter.
4. **"Identical" cars aren't identical.** The two F-150s from the same package weigh 38g and 31.5g — they're 20% different! You have to actually weigh things, not just assume.
5. **Where you put the weight matters.** The VW Truck without the roof sensor was faster than the one with it, even though it weighed more. Putting weight on the roof makes the car wobbly.
6. **The ride-along sensor proved real forces are happening.** The cars feel up to 2.5 times gravity on a normal run. During the crash, the car was spinning at 339 RPM and hit with 4 times gravity.

---

## ANALYSIS

Adding weight to a Hot Wheels car doesn't just make it faster or slower — it depends on how much weight you add and how heavy the car already is.

**Why a little weight helps:** When a car is at the top of the ramp, it has stored energy (called potential energy). A heavier car has more stored energy. When it rolls down, that energy turns into speed (kinetic energy). So more weight = more energy = a little faster.

**Why too much weight hurts:** At some point, the extra weight makes the wheels rub harder against the axles and the track. That's called friction. The tiny wheels on Hot Wheels cars can't handle a lot of extra weight. The Control car was already heavier, so it hit its friction limit first.

**The two "identical" cars were really different.** I thought they would weigh the same because they're the same model from the same package. But one weighs 38g and the other weighs 31.5g — that's a 6.5 gram difference (20.5%!). This taught me that in science, you can't just assume things are the same. You have to measure.

**About the bad run:** One run came in at 1.687 seconds, way slower than all the others (around 1.48–1.51s). The car probably bumped the wall. I ran an extra trial to replace it. Scientists deal with weird results by running more trials and writing down what happened.

**What the ride-along sensor taught me:** When I taped the sensor to the roof of the VW Truck, the car was slower and crashed once. When I took the sensor off, the same truck was faster — even though it was slightly heavier just from the tape. This tells me that where you put the weight is just as important as how much weight you add. Weight on the roof makes the car top-heavy and unstable.

**How accurate is the data?** The M.A.S.S. Trap measures time to 0.001 seconds. But the start gate and finish gate are on different computers that talk to each other wirelessly, so there's about ±10 milliseconds of wobble in the timing. That's random though (not always too high or too low), so averaging 3 trials smooths it out. The differences between my conditions (about 27 milliseconds) are bigger than the wobble, so the patterns in my data are real.

---

## CONCLUSION

My hypothesis was **partly right**. I said adding weight would make the cars faster because of more energy. That was true when I added a little bit of weight (3.5g or 7g). But it wasn't true for the heavier car when I added 14g — that car actually got slower.

The real answer is cooler than what I guessed: **there's a best weight for going the fastest.** A little extra weight gives the car more energy to push through friction. But too much weight creates so much friction that it slows the car down. The lighter car had more room before it hit the friction limit, which is why it kept getting faster.

**Things I would do differently next time:**
1. Try more weight amounts (1g, 2g, 3g, 4g... up to 20g) to find the exact best weight
2. Use 3 or more different cars to see if the pattern is the same
3. Try putting the weight in different spots (front, back, on top) to see if placement matters — the crash data already showed that putting weight on the roof is bad
4. Fix the broken motion sensor and record what the car feels at every weight level

---

## APPLICATION (How This Connects to Real Life)

1. **Race cars:** NASCAR and F1 teams spend tons of money finding the perfect weight for their cars. Too light and they don't grip. Too heavy and they're slow. My experiment showed the same thing with Hot Wheels.

2. **Roller coasters:** Roller coasters use the same idea — a heavier car at the top of the hill has more energy. That's why a car full of adults goes a little differently than a car full of kids.

3. **Factory quality control:** I found out that two "identical" Hot Wheels trucks are actually 20% different in weight. In real factories that make airplane parts or medicine, parts that are supposed to be the same HAVE to be the same, or bad things happen.

4. **Airplane black boxes:** My ride-along sensor worked like the black box in an airplane. After the crash, I could see exactly what happened — how fast it was spinning, how hard it hit, and which side it landed on. Real crash investigators do the same thing.

5. **The scientific method:** I learned that you can't just guess. I thought heavier = faster, and I was only partly right. Without actually measuring, I would have gotten the wrong answer.

---

*Data collected with the M.A.S.S. Trap (Motion Analysis & Speed System) — built by Ben Massfeller and his dad.*
*Track: 5.85 meters | Scale: 1:64 | Sensors: Infrared | Precision: ±0.001 seconds*
*25 runs collected February 17, 2026 | 14 runs collected February 19, 2026*
