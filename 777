import pandas as pd

def friendship_timeline(friends_added, friends_removed):
    friendadd = pd.DataFrame(friends_added)
    friendrmv = pd.DataFrame(friends_removed)
    user_ids = []
    start_date = []
    end_date = []
    

    for i in friendadd['user_ids']:
        i.sort()
    
    for j in friendrmv['user_ids']:
        j.sort()

    i = 0
    j = 0
    add_n = friendadd.shape[0]
    rmv_n = friendrmv.shape[0]

    friendadd.sort_values(by='user_ids', inplace=True)
    friendrmv.sort_values(by='user_ids', inplace=True)

    while i < add_n and j < rmv_n:
        if friendadd['user_ids'][i] == friendrmv['user_ids'][j]:
            user_ids.append(friendadd['user_ids'][i])
            start_date.append(friendadd['created_at'][i])
            end_date.append(friendrmv['created_at'][j])
            i+=1
            j+=1
        else:
            i+=1
    
    column_names = ["user_ids", "start_date", "end_date"]
    friendship1 = pd.DataFrame(columns = column_names) 
    friendship1.user_ids = user_ids
    friendship1.start_date = start_date
    friendship1.end_date = end_date 
    friend_timeline=friendship1.to_dict('records')
    return  friend_timeline 
