States 1-12: TM for Diff(n,m).
        
States 21-23: Convert $ to (n,0).
        
States 31-55: Duplicate (n,m) to (n,m,n,m).
        
States 61-62: Check if g(n,m) = 0.
        
States 71-76: If g(n,m) != 0, replace (n,m) with (n,m+1), then repeat (2).
        
States 81-90: If g(n,m) = 0, return m. 