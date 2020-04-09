
```
for f in *.png; do
convert  $f -resize 25\% ${f/.png/_25pct.png}
done
```
