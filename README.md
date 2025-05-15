
# CLIPS Tasks

## Student Information
- **Name:** Abdelrahman Ashraf Elsaid
- **Section Number:** 4

---

## Task 1: Hair Color Check Rule

### Description
Write a CLIPS rule called `check_color` that prints the hair color of a person, given that the color is neither black nor brown.

### CLIPS Code

```clips
(clear)

(deftemplate individual
   (slot hair-color))

(defrule check_color
   (individual (hair-color ?c&~black&~brown))
   =>
   (printout t "Hair color is: " ?c crlf))

(assert (individual (hair-color red)))
(assert (individual (hair-color blonde)))
(assert (individual (hair-color black)))
(assert (individual (hair-color brown)))

(run)
```

### Expected Output

```
Hair color is: blonde
Hair color is: red
```

---

## Task 2: Define Person Template with Constraints

### Description
Define a CLIPS template for a person where:

- The `name` field accepts either symbols or strings,
- Must contain between 2 to 4 items,
- The `age` field is an integer restricted to values between 20 and 25.

### CLIPS Code

```clips
(deftemplate person
  (multislot name
    (type SYMBOL STRING)
    (cardinality 2 4))
  (slot age
    (type INTEGER)
    (range 20 25)))
```

### Example Usage

```clips
(assert (person (name "Abdelrahman" "Ashraf") (age 22)))
```

---
