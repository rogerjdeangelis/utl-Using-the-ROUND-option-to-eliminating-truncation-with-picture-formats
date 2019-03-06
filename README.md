# utl-Using-the-ROUND-option-to-eliminating-truncation-with-picture-formats
Using the ROUND option to eliminating truncation with picture formats     
    Using the round option to eliminating truncation with picture formats               
                                                                                        
    *                _     _                                                            
     _ __  _ __ ___ | |__ | | ___ _ __ ___                                              
    | '_ \| '__/ _ \| '_ \| |/ _ \ '_ ` _ \                                             
    | |_) | | | (_) | |_) | |  __/ | | | | |                                            
    | .__/|_|  \___/|_.__/|_|\___|_| |_| |_|                                            
    |_|                                                                                 
    ;                                                                                   
                                                                                        
    proc format;                                                                        
     picture Pct low - high = '009.9%' ( mult=1000)                                     
    ;run;quit;                                                                          
                                                                                        
    data have;                                                                          
      input CC_rates ;                                                                  
      put  cc_rates pct.;                                                               
    cards4;                                                                             
    0.00099                                                                             
    1.0                                                                                 
    0.49999                                                                             
    ;;;;                                                                                
    run;quit;                                                                           
                                                                                        
    RESULT     SHOULD BE                                                                
    ======     =========                                                                
                                                                                        
      0.0%        0.1%                                                                  
    100.0%      100.0%                                                                  
     49.9%       50.0%                                                                  
                                                                                        
    *          _       _   _                                                            
     ___  ___ | |_   _| |_(_) ___  _ __                                                 
    / __|/ _ \| | | | | __| |/ _ \| '_ \                                                
    \__ \ (_) | | |_| | |_| | (_) | | | |                                               
    |___/\___/|_|\__,_|\__|_|\___/|_| |_|                                               
                                                                                        
    ;                                                                                   
                                                                                        
    proc format;                                                                        
                 ******;                                                                
     picture Pct (ROUND) low - high = '009.9%' ( mult=1000)                             
    ;run;quit;   ******;                                                                
                                                                                        
    data have;                                                                          
      input CC_rates ;                                                                  
      put  cc_rates pct.;                                                               
    cards4;                                                                             
    0.00099                                                                             
    1.0                                                                                 
    0.49999                                                                             
    ;;;;                                                                                
    run;quit;                                                                           
                                                                                        
      0.1%                                                                              
    100.0%                                                                              
     50.0%                                                                              
                                                                                        
                                                                                        
