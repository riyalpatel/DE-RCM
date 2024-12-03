# DE-RCM
Technology Azure Data Engineering Stack
Domain - Healtcare Revenue Cycle Management (RCM)
RCM is the process that hospital use to manage the finaccial aspects, from the time the patient schedule an appintment till the time the provider gets paid.

Simplifide breakdown

1. It start with a patient visit:
     Patient details are collected, Isurance Details..
     This ensures provider knows who will pay for the services
     insurance, the patient or both

2. Servies are provided:
    Recored are made

3. Billing :
    Hospital will create the bill and send to payer

4. Claims Are Reviewed :
    Isurance Company review the bill

5. payments and followups may happen:
     if partial is done by insurance comapny then remaining are given by the patient and hospitals/ provider will follow up

6. Tracing and followups

RCM ensures the hospital can provide quality care while also staying financially healty.

As part of RCM we have 2 main aspects
1. account Receviable (AR)
2. accounts payable
   we will focuse on accounts receviable

Patient paying is often a rist

senario when patient has to pay

Low Insurance - these insurance prpvide put most of the burden on patients..

Private Clinics 
Dental Treatments
Deductibles

2 Objective for AR
-Bring Case
- minimize the collection period

the probability of collecting your full amount decreases with time..
93% of money due 30 days old
85% of money due 60 days old
73% of money due 90 days old 

KPI to mesure AR and Set benchmarks..
1. AR > 90 days


Data Engineer Pipeline
===========================
DE What I am gone do 
I will have various sources

- create Pipeline
- Result of this pipeline AS FactTabels and Dimension tables,
- this will help reporting team to genrate KPI

Detasets
=======
EMR Data (Electronic Medial Records) (_____Azure SQL DB)
  -Patient
  -Providers
  -Department
  -Transection
  -Encounter
Claims Data (_____Flat Files)
  -Isurance Company 
  - Flat flies (Monthly Once)
  
NPI Data (National Proivider Identifier) (_____API)

ICD Data (Standerdise System used by health care providers map diagnostic) (______API)


Solution Architecture
==================
Medallion Architecture

Landing    ->  Bronze         ->  Silver        ->  gold
Flat file  ->  Parquet files  ->  Delta tables  ->  Delta tables



===================
ERM -> ADLS Gen2
we will create a audit table (delta lake)
 to save details of pipeline runs

 























