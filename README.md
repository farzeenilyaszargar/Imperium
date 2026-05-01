## Imperium Capital

this is my automatic trading system for the indian stock market that executes trades for me daily using my ₹100 on a daily basis.

#### Stack
- .py code for the algos
- broker & api is **dhanHQ api**
- cron job
- sql (local db)
- dashboard (local website reading from local db) 


#### Basic Algo Idea

We calculate 4 things
- Analyze market trends using technical indicators
- Analyze social media sentiment trends
- Analyze economic trends
- Analyze and evalute a company's stock performance and financials


We plan if we want to buy -->
- Stock are bought based on this formula

   <p style="font-style: mono"> 
   Final Score = (

    # QUALITY (30%)
    0.30 * (
        0.25 * ROE_score +
        0.20 * ROCE_score +
        0.20 * Operating_Margin_score +
        0.20 * FCF_Consistency_score +
        0.15 * Net_Profit_Margin_score
    )

    # GROWTH (25%)
    + 0.25 * (
        0.35 * Revenue_CAGR_score +
        0.35 * EPS_CAGR_score +
        0.15 * FCF_Growth_score +
        0.15 * Earnings_Stability_score
    )

    # VALUATION (20%)
    + 0.20 * (
        0.30 * Intrinsic_Discount_score +
        0.25 * PE_score +
        0.20 * PB_score +
        0.15 * EV_EBITDA_score +
        0.10 * PFCF_score
    )

    # MOMENTUM (10%)
    + 0.10 * (
        0.50 * RS_6M_score +
        0.30 * RS_12M_score +
        0.20 * Trend_score
    )

    # CAPITAL EFFICIENCY (5%)
    + 0.05 * (
        0.50 * Asset_Turnover_score +
        0.50 * FCF_Margin_score
    )

    # RISK PENALTY (subtract)
    - 0.10 * (
        0.35 * Debt_score +
        0.20 * Pledge_score +
        0.15 * Interest_Coverage_risk +
        0.15 * Earnings_Volatility_score +
        0.15 * Dilution_score
    )

    )
    </p>