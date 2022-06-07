# InvestAI Backend Task

This backend exercise involves building a Node.js service that will serve a REST API through HTTP. We imagine you should spend around 6 hours implementing this service

# FixedIncomeOffer

A FixedIncomeOffer is an asset that is currently being sold and can be bought by some **Buyer**

```ts
interface FixedIncomeOffer {
	id: string;
	availableQuantity: number; // e.g. 100
	unitPrice: number; // e.g. 1000
	yieldRate: number; // e.g. 0.10 (10% yearly)
}
```

The `yieldRate` tells how much interest rate this asset pays per year. So for example this asset pays 10% interest rate per year.

The `unitPrice` represents the minimum amount (in R$) that can be bought of this asset. The amount a buyer can buy of any asset will always be a quantity (which is a natural number) times its `unitPrice`.

Tip1: Here in Brazil we use compound interest rate for all calculations

Tip2: The asset yields interest rate every business day, and one year has 252 business days

## Task 1

Implement a REST endpoint to CREATE `FixedIncomeOffers`. 

## Task 2

Implement a REST endpoint to buy `FixedIncomeOffers`. It receives the buyer `id`, the `fixedIncomeOfferId` and the `quantity` desired.

## Task 3

Implement a REST endpoint to retrieve all the assets purchased by particular buyer by its id.

## Task 4

Implement a REST endpoint that, given a date in the future and a buyer, returns the total amount of money that this customer will have in that date considering all the assets he has bought until now.

## Some Technical Requisites

- The state of the service (offers, purchases, etc) must be persisted even between different runs of the service. i.e. The service must keep its state even if we kill the main process.
- It should not be allowed in any circumstance that buyers end up buying more than the specified quantity of an asset, even under heavy load.
- We are talking about money here! 🤑 So be careful while you are doing the calculations to not propagate rounding errors.

## Going Above and Beyond the Requirements

Given the time expectations of this exercise, we don't expect anyone to submit anything super fancy, but if you find yourself with extra time, any extra features that showcase your unique strengths would be awesome! 🙌

It would be great for example if you'd write some authentication logic / simple frontend demostrating calls to your fresh APIs.

Here at InvestAI we value a lot automated testing and Test Driven Development. So it would be great too if you could write some tests while you are at it.
