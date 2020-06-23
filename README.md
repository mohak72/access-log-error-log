# access-log-error-log
https://easyengine.io/tutorials/nginx/log-parsing/
cat access.log | cut -d '"' -f3 | cut -d ' ' -f2 | sort | uniq -c | sort -rn
awk '{print $9}' access.log | sort | uniq -c | sort -rn
awk '($9 ~ /404/)' access.log | awk '{print $7}' | sort | uniq -c | sort -rn
awk '($8 ~ /404/)' access.log | awk '{print $8}' | sort | uniq -c | sort -rn
awk '($9 ~ /502/)' access.log | awk '{print $7}' | sort | uniq -c | sort -r
awk -F\" '($2 ~ "/wp-admin/install.php"){print $1}' access.log | awk '{print $1}' | sort | uniq -c | sort -r
awk '($9 ~ /404/)' access.log | awk -F\" '($2 ~ "^GET .*\.php")' | awk '{print $7}' | sort | uniq -c | sort -r | head -n 20
awk -F\" '{print $2}' access.log | awk '{print $2}' | sort | uniq -c | sort -r #most requested url
