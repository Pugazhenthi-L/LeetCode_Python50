# LeetCode_Python50

<summary>Select</summary> 

Q-1) https://leetcode.com/problems/recyclable-and-low-fat-products/submissions/?envType=study-plan-v2&envId=top-sql-50

    import pandas as pd
    def find_products(products: pd.DataFrame) -> pd.DataFrame:
        result = products[(products["low_fats"] == "Y") & (products["recyclable"] == "Y")]
        result = result[["product_id"]]
        return result

Q-2) https://leetcode.com/problems/find-customer-referee/?envType=study-plan-v2&envId=top-sql-50

    import pandas as pd
    def find_customer_referee(customer: pd.DataFrame) -> pd.DataFrame:
        result = customer[(customer["referee_id"]!=2) | (customer["referee_id"].isnull())]
        result = result[["name"]]
        return result

Q-3) https://leetcode.com/problems/big-countries/?envType=study-plan-v2&envId=top-sql-50

    import pandas as pd
    def big_countries(world: pd.DataFrame) -> pd.DataFrame:
        result = world[(world["population"]>=25000000) | (world["area"]>=3000000)]
        result = result[["name","population","area"]]
        return result

Q-4) https://leetcode.com/problems/article-views-i/?envType=study-plan-v2&envId=top-sql-50

    import pandas as pd
    import numpy as np
    
    def article_views(views: pd.DataFrame) -> pd.DataFrame:
        result_df = views[views['author_id'] == views['viewer_id']]
    
        unique_author_ids = result_df['author_id'].unique()
        sorted_unique_author_ids = np.sort(unique_author_ids)
        
        result_df = pd.DataFrame({'id': sorted_unique_author_ids})
        
        return result_df

Q-5) https://leetcode.com/problems/invalid-tweets/?envType=study-plan-v2&envId=top-sql-50

    import pandas as pd
    
    def invalid_tweets(tweets: pd.DataFrame) -> pd.DataFrame:
        result = tweets[tweets["content"].str.len() > 15]["tweet_id"]
        result_d = pd.DataFrame({"tweet_id" : result})
        return result_d

## Basic Joins

Q-6) https://leetcode.com/problems/replace-employee-id-with-the-unique-identifier/?envType=study-plan-v2&envId=top-sql-50
    
