'''
My json to csv conversion script attempt
v.10
8/9/16
 
Create a Reddit App and Fill in your information. This is a script for the public. No need for keys or auth tokens
'''
 
import praw
from datetime import date
 
ua = ('XPCPRO top release monitor - json to csv u/tehmass v .10'
     'Url: https://diy.yolodigi.com/'
     'wiki/json2csv.html')
 
r = praw.Reddit(user_agent=ua, site_name='your_bot')
sub_choice = raw_input('would you like to choose a subreddit?:')
subreddit = r.get_subreddit(sub_choice)
def main(sub_choice):
    if sub_choice is False:
        sub_choice = raw_input('What SubReddit would You like today?:')
        sub_type = raw_input("new or top?:")
        if sub_type == new:
            sbreddit_new()
        elif sub_type == top:
            sbreddit_top()
        else:
            print('False')
            sub_type = raw_input("new or top? [lowercase please!!]:")
    else:
        sub_type = raw_input("new or top?:")
        print('else')
        if sub_type == 'new':
            sbreddit_new(sub_choice)
        elif sub_type == 'top':
            sbreddit_top(sub_choice)
        else:
            print('Else/Else')
            sub_type = raw_input("new or top? [lowercase please!!]:")
            return
def sbreddit_new(sub_choice):
    title = list()
    url = list()
 
    r = praw.Reddit(user_agent=ua, site_name='your_bot')
    subreddit = r.get_subreddit(sub_choice)
    sbredt_new = subreddit.get_new(limit=10)
 
    for post in sbredt_new:
        while post.title not in list(title):
            title.append(post.title)
            url.append(post.url)
 
    import csv
    from itertools import izip
 
    ofile  = open('test.csv', "a")
    writer = csv.writer(ofile, delimiter='|', quotechar='"', quoting=csv.QUOTE_NONE)
    writer.writerow((' '))
    writer.writerow( ('NEW FOR THE DAY', 'Title', 'URL', date.today() ))
    writer.writerows(izip(title, url))
 
    ofile.close()
 
 
def sbreddit_top(sub_choice):
    title = list()
    url = list()
 
    r = praw.Reddit(user_agent=ua, site_name='your_bot')
    subreddit = r.get_subreddit(sub_choice)
    sbredt_top = subreddit.get_top_from_day(limit=15)
 
    for post in sbredt_top:
        while post.title not in list(title):
            title.append(post.title)
            url.append(post.url)
 
    import csv
    from itertools import izip
 
    ofile  = open('test.csv', "a")
    writer = csv.writer(ofile, delimiter='  ', quotechar='"', quoting=csv.QUOTE_NONE)
    writer.writerow((' '))
    writer.writerow( ('TOP FOR THE DAY', 'Title', 'URL', date.today() ) )
    writer.writerows(izip(title, url))
 
    ofile.close()
 
 
main(sub_choice)
