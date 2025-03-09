import pandas as pd

def largest_orders(orders: pd.DataFrame) -> pd.DataFrame:
    orders = orders.groupby('customer_number').size().reset_index(name='cnt')
    df = orders.sort_values('cnt',ascending=False)
    return df[['customer_number']].head(1)