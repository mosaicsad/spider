# -*- coding:utf-8 -*-
import urllib
import urllib2
import re


page = 1
url = "http://www.qiushibaike.com/hot/page/" + str(page)
#add head
user_agent = "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_13_1) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/63.0.3239.132 Safari/537.36"
headers = { 'User-Agent': user_agent}
try:
	request = urllib2.Request(url, headers = headers)
	response = urllib2.urlopen(request, timeout = 2)
	content = response.read().decode('utf-8')
	pattern = re.compile('<div class="author clearfix">.*?<h2>(.*?)</h2>.*?"content"><span>(.*?)</span>.*?</div>.*?number">(.*?)</.*?number">(.*?)</.', re.S)
	#pattern = re.compile('h2>(.*?)</h2.*?content.*?span>(.*?)</.*?!--.*?-->(.*?)</.*?number>(.*?)</i>', re.S)
	items = re.findall(pattern, content)
	items = str(items).replace('u\'','\'')#必须记下来
	
	print items
	#print response.read()
except urllib2.URLError, e:
	if hasattr(e, "code"):
		print e.code
	if hasattr(e, "reason"):
		print e.reason
print u'\u65e0\u5948\u604b\u4e0a\u4f60\u7684chu\u2026'
