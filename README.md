#!/usr/bin/python
# -*- coding: utf-8-*-

import requests;

import json;


for m in range(1,100):

    url ="https://rate.tmall.com/list_detail_rate.htm?itemId=531867931310&spuId=574477483&sellerId=2888462616&order=3&currentPage="+str(m)


    res=requests.get(url).text[12:-1]

    # print(res)

    # print(type(res))

    a=json.loads(res)

    b=a["rateDetail"]["rateList"]

    for i in b:
        try:


            with open("a.txt","a+") as f:

               f.write( i["rateContent"])+"\n"

        except:

            continue;

