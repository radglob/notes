## Sections to Cover
- Chapter 1 [COMPLETED]
- Chapter 2.1 - 2.5 [COMPLETED]
- Chapter 3.1 - 3.4 [COMPLETED]
- Chapter 4.1 - 4.3 [COMPLETED]
- Chapter 5.1 - 5.5 (except continuous random variable joint distributions) [COMPLETED]
- Chapter 7.1 - 7.3 [COMPLETED]
- Chapter 8.1, .2, .4
- Chapter 0.1 - 9.3

### Chapter 1:
Key Things to remember:
- 1.1: This section has a bunch of simple definitions.
  - Inferential statistics: the mathy crap we actually do.
  - Descriptive statistics: pretty graphs and such.
- 1.2: Graphs and crap.
  - Stem and leaf, box plot, etc.
- 1.3: Mean, trimmed means, median, quartiles.
- 1.4: Variance and standard deviation.
  - Know these formulas.

### Chapter 2:
Key Things to Remember:
- 2.1: Sample spaces, events, basic set theory.
- 2.2: Basic probablistic axioms:
  - P(A || B) = P(A) + P(B) - P(A &amp; B)
- 2.3: Counting... Permutations and Combinations are key here.
  - Permutations: P_(k,n) = n! / (n - k)!
  - Combinations: C_(k,n) = n! / k!(n - k)!
- 2.4: Conditional Probability:
  - P(A | B) = P(A &amp; B) / P(B)
  - Multiplication Rule: P(A &amp; B) = P(A | B) * P(B).
  - Baye's Theorem: P(A(i) | B) = P(A(i) &amp; B) / P(B) = ...
- 2.5: Independence
  - Two events A and B are independent if P(A | B) = P(A), otherwise ::
    dependent.
  - A and B are independent iff P(A &amp; B) = P(A) * P(B)

### Chapter 3:
Key Things to Remember:
- 3.1: Random Variables:
  - Discrete, continuous, Bernoulli :: single event; binomial :: multiple
      events.
- 3.2: Probability Distributions:
  - PMF: P(X = x) = P(all s in S: X(s) = x)
  - CDF: F(X) = P(X &lte; x) = sum(p(y))
- 3.3: Expected Value of X:
  - E(X) = mean of x = sum of all x * p(x)
  - E(aX + b) = a * E(x) + b
  - V(X) = E[(X - mu)^2] || E(X^2) - [E(X)]^2
  - SD(x) = sqrt(V(x))
- 3.4: Binomial Probability Distribution

### Chapter 4:
Key Things to Remember:
- 4.1: Probability Density Functions of Continuous Random Variables
  - Integrals, yo.
  - pdf :: P(a &lte; X &lte; b) = the integral from a to b of f(x)dx
  - Uniform distribution: f(x;A,B) = if A &lte; x &lte; B = 1/ B - A else = 0
- 4.2: CDF and E(X) 
  - cdf :: F(x) = P(X &lte; x) = the integral from negative infinity to x of
      f(y)dy
  - (100p)th percentile: p = F(eta(p)) = integral from negative infinity to
      eta(p) of f(y)dy.
  - Median of a continuous distribution is the 50th percentile.
  - E(X) = integral from negative infinity to positive infinity of x * f(x)dx
  - V(x) = integral from negative infinity to positive infinity of (x - mu)^2 *
      f(x)dx = E[(X - mu)^2]
  - SD(x) = sqrt(V(x)
- 4.3: The Normal Distribution
  - Standard Normal Distribution: f(z;0,1) = [1 / sqrt(2pi)]e^(z^2 / 2),
    -infinity &lte; z &lte; infinity
  - Most of this stuff isn't useful in practice. Know to normalize data and use
    the tables.

### Chapter 5:
Key Things to Remember:
- 5.1: Joint Probability:
  - joint pmf p(x,y) = P(X = x and Y = y)
  - marginal pmf p_x(x) = sum p(x,y) for all x
  - marginal pmf p_y(y) = sum p(x,y) for all y
  - joint pdf = P[(X,Y) in A] = integral(a,b) integral(c,d) f(x,y) * dy * dx
  - marginal pdf f_x(x) = integral(-inf, inf) f(x,y)dy for all x
  - marginal pdf f_y(y) = integral(-inf, inf) f(x,y)dx for all y
  - Independent RVs iff
    - p(x,y) = p.x(x) * p.y(y) when X and Y are discrete.
    - f(x,y) = f.x(x) * f.y(y) when X and Y are continuous.
  - Conditional p[dm]f:
  - conditional pdf :: f.(y|x)(y|x) = f(x,y) / f.x(x) where -inf &lt; y &lt; inf
  - conditional pmf :: replace pdfs above with pmfs.
- 5.2: E(X), Covariance, Correlation:
  - expected value of h(X,Y) = 
    - sum.x sum.y h(x,y) * p(x,y) if X and Y are
      discrete.
    - int(-inf, +inf) int(-inf, +inf) h(x,y) * f(x,y) * dx * dy if X and Y are
      continuous.
  - covariance: Cov(X,Y) = E[(X -mu.x)(Y - mu.y)] =
    - sum.x sum.y (x - mu.x)(y - mu.y)p(x,y) | X, Y :: discrete
    - int(-inf, +inf) int(-inf, +inf) (x - mu.x)(y - mu.y) * f(x,y) * dx * dy |
      X, Y :: continuous
    - Shorthand: Cov(X,Y) = E(XY) - mu.x * mu.y
  - Correlation coefficient Corr(X,Y) = Cov(X,Y) / sigma.x * sigma.y
- 5.3: Statistics and their distributions
  - Sample size is a useful factor for approximating normal distributions.
- 5.4: Distribution of the Sample Mean
  - Central Limit Theorem: Let [X] be a random sample from a distribution with
    mean mu and variance sigma^2. Then if n is sufficiently large, X.bar has
    approximately a normal distribution with mu.x.bar = mu and sigma.x.bar^2 =
    sigma^2 / n and T.0 also has approximately a normal distribution with
    mu.t.0 = n.mu, sigma.T.0^2 = n*sigma^2. The larger the value of n, the
    better the approximation.
  - General rule of thumb: n &gte; 30 is considered large.
- 5.5 Distribution of a Linear Combination:
  - A linear combination of X.i's :: Y = a.i * X.i + ... + a.n * X.n = sum(i=1,
      n){a.i * X.i}

### Chapter 7;
Things to remember:
- 7.1: Basic Properties of Confidence Intervals [N(mu, sigma=known)]:
  - 100(1 - alpha)% CI with mean mu when sigma is known :: (x.bar +- z.alpha/2 *
      sigma/sqrt(n))
  - Sample size necessary for CI to have width of w :: n = (2z.alpha/2 * sigma /
      w)^2
- 7.2: Large Sample Confidence Intervals [_(mu, sigma=unknown), n &gt; 30]
  - If n is sufficiently large, we can standardize to a z table :: Z = (X.bar -
      mu) / (S / sqrt(n))
  - Large sample upper confidence bound for mu :: mu &lt; x.bar + z.alpha * s /
      sqrt(n)
  - Large sample lower confidence bound for mu :: mu &gt; x.bar - z.alpha * s /
      sqrt(n)
- 7.3: Intervals based on a Normal Population Distribution [N(mu=unknown,
    sigma=unknown), n &lt; 30]
  - When X.bar is the mean of a random sample of size n from a normal
      distribution with mean mu, the rv T = X.bar - mu / S / sqrt(n)
  - 100(1 - alpha)% confidence interval for mu :: (x.bar +- t.alpha/2,n-1 * s /
      sqrt(n))
  - Prediction interval :: x.bar +- t.alpha/2,n-1 * s * sqrt(1 + 1/n)

### Chapter 8:
Things to remember:
- 8.1: Hypotheses and Test Procedures:
  - Null hypothesis (H.0) is the claim asserted that is initially assumed to be
    true.
  - Alternative hypothesis (H.a) is the assertion that is contradictory to the
    null hypothesis.
  - Test statistic is a function of the sample data which the decision (to
    reject or not) is based upon.
  - Rejection region is the set of all test statistic values for which H.0 will
    be rejected.
  - Errors:
    - Type I Error: P(Reject H.0 | H.0 is true)
    - Type II Error: P(Don't reject H.0 | H.0 is false)
