# How to calculate your one-rep max using TypeScript

If you're a weightlifter or powerlifter, you're probably familiar with the concept of a "one-rep max" (1RM). This is the maximum amount of weight you can lift for a single repetition of a given exercise. Knowing your 1RM can be useful for tracking progress, planning workouts, and setting goals.


If you prefer not to calculate your 1RM manually there are many online calculators available that will do the calculations for you such as this [one-rep max calculator](https://1rmcalculator.com/) which is more accurate at higher reps and is feature rich.

## Scientific Principles
The concept of the one-rep max (1RM) is based on the idea of maximum muscular strength. When you lift a weight, you're using your muscles to generate force. The amount of force your muscles can generate depends on a number of factors, including muscle fibre type, muscle cross-sectional area, and neural adaptations. The 1RM represents the maximum amount of force that your muscles can generate for a single repetition.

To calculate your 1RM, you typically perform a set of an exercise for as many reps as possible, using a weight that's heavy enough to make it difficult to complete the last few reps. Based on the weight and number of reps you were able to perform, you can estimate your 1RM using a formula.

## Estimating Your 1RM

There are several different formulas that can be used to estimate your 1RM. Here are a few of the most commonly used formulas:

### Epley Formula
The Epley formula is one of the most commonly used formulas for estimating your 1RM. It's based on the relationship between the weight lifted and the number of reps performed and takes into account the fact that lifting a heavier weight for fewer reps requires more strength than lifting a lighter weight for more reps. The formula is as follows:

`1RM = weight_lifted x (1 + (reps_performed / 30))`

Here's how you can implement the Epley formula in TypeScript:

```typescript
function calculate1RMUsingEpley(weight: number, reps: number): number {
  const max = weight * (1 + reps/30);
  return Math.round(max);
}
```

### Brzycki Formula
The Brzycki formula is another commonly used formula for estimating your 1RM. It's similar to the Epley formula but uses a slightly different coefficient to account for the fact that heavier weights require more strength to lift. The formula is as follows:

`1RM = weight_lifted x (36 / (37 - reps_performed))`

Here's how you can implement the Brzycki formula in TypeScript:

```typescript
function calculate1RMUsingBrzycki(weight: number, reps: number): number {
  const max = weight * (36 / (37 - reps));
  return Math.round(max);
}
```

### Lombardi Formula
The Lombardi formula is a third formula that can be used to estimate your 1RM. It's based on the weight lifted and the number of reps performed and takes into account the fact that the relationship between these two factors is not linear. The formula is as follows:

`1RM = weight_lifted x reps_performed^0.10`

Here's how you can implement the Lombardi formula in TypeScript:

```typescript
function calculate1RMUsingLombardi(weight: number, reps: number): number {
  const max = weight * Math.pow(reps, 0.10);
  return Math.round(max);
}
```
