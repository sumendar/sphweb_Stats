```{.python .input  n=2}
height <- c(58,59,60,61,62,63,64,65,66, 67, 68, 69, 70, 71, 72)
weight <- c(115,117,120,123,126,129,132,135,139, 142, 146, 150, 154, 159, 164)
```

```{.python .input  n=3}
htwtmatrix = matrix(c(height,weight),15,2) # what do 15 and 2 refer to?
```

```{.python .input  n=4}
print(htwtmatrix)
dim(htwtmatrix)
is.array(htwtmatrix)  
# even its a matrix it will return TRUE, because matrix also a type of array in 2 dimentional 

```

```{.json .output n=4}
[
 {
  "name": "stdout",
  "output_type": "stream",
  "text": "      [,1] [,2]\n [1,]   58  115\n [2,]   59  117\n [3,]   60  120\n [4,]   61  123\n [5,]   62  126\n [6,]   63  129\n [7,]   64  132\n [8,]   65  135\n [9,]   66  139\n[10,]   67  142\n[11,]   68  146\n[12,]   69  150\n[13,]   70  154\n[14,]   71  159\n[15,]   72  164\n"
 },
 {
  "data": {
   "text/html": "<ol class=list-inline>\n\t<li>15</li>\n\t<li>2</li>\n</ol>\n",
   "text/latex": "\\begin{enumerate*}\n\\item 15\n\\item 2\n\\end{enumerate*}\n",
   "text/markdown": "1. 15\n2. 2\n\n\n",
   "text/plain": "[1] 15  2"
  },
  "metadata": {},
  "output_type": "display_data"
 },
 {
  "data": {
   "text/html": "TRUE",
   "text/latex": "TRUE",
   "text/markdown": "TRUE",
   "text/plain": "[1] TRUE"
  },
  "metadata": {},
  "output_type": "display_data"
 }
]
```

```{.python .input  n=5}
# to assign names for each column first convert it into a dataframe
htwtdata = data.frame(htwtmatrix)  # as.dataframe is also works well here
names(htwtdata) = c("height", "weight")
# here we used names() function to assign the names for our dataframe
names(htwtdata)  # here we are extracting the names , names function can be used to set or get the names

```

```{.json .output n=5}
[
 {
  "data": {
   "text/html": "<ol class=list-inline>\n\t<li>'height'</li>\n\t<li>'weight'</li>\n</ol>\n",
   "text/latex": "\\begin{enumerate*}\n\\item 'height'\n\\item 'weight'\n\\end{enumerate*}\n",
   "text/markdown": "1. 'height'\n2. 'weight'\n\n\n",
   "text/plain": "[1] \"height\" \"weight\""
  },
  "metadata": {},
  "output_type": "display_data"
 }
]
```

```{.python .input  n=6}
# Let us see how R operates on matrices, and how that compares to data frames
htwtmatrix * 2  # multiplying with 2 gives us result of multiplication on each value 
htwtmatrix[, 1]/12  # convert height in inches to feet
mean(htwtmatrix[, 2])  # find mean of weight
```

```{.json .output n=6}
[
 {
  "data": {
   "text/html": "<table>\n<tbody>\n\t<tr><td>116</td><td>230</td></tr>\n\t<tr><td>118</td><td>234</td></tr>\n\t<tr><td>120</td><td>240</td></tr>\n\t<tr><td>122</td><td>246</td></tr>\n\t<tr><td>124</td><td>252</td></tr>\n\t<tr><td>126</td><td>258</td></tr>\n\t<tr><td>128</td><td>264</td></tr>\n\t<tr><td>130</td><td>270</td></tr>\n\t<tr><td>132</td><td>278</td></tr>\n\t<tr><td>134</td><td>284</td></tr>\n\t<tr><td>136</td><td>292</td></tr>\n\t<tr><td>138</td><td>300</td></tr>\n\t<tr><td>140</td><td>308</td></tr>\n\t<tr><td>142</td><td>318</td></tr>\n\t<tr><td>144</td><td>328</td></tr>\n</tbody>\n</table>\n",
   "text/latex": "\\begin{tabular}{ll}\n\t 116 & 230\\\\\n\t 118 & 234\\\\\n\t 120 & 240\\\\\n\t 122 & 246\\\\\n\t 124 & 252\\\\\n\t 126 & 258\\\\\n\t 128 & 264\\\\\n\t 130 & 270\\\\\n\t 132 & 278\\\\\n\t 134 & 284\\\\\n\t 136 & 292\\\\\n\t 138 & 300\\\\\n\t 140 & 308\\\\\n\t 142 & 318\\\\\n\t 144 & 328\\\\\n\\end{tabular}\n",
   "text/markdown": "\n| 116 | 230 | \n| 118 | 234 | \n| 120 | 240 | \n| 122 | 246 | \n| 124 | 252 | \n| 126 | 258 | \n| 128 | 264 | \n| 130 | 270 | \n| 132 | 278 | \n| 134 | 284 | \n| 136 | 292 | \n| 138 | 300 | \n| 140 | 308 | \n| 142 | 318 | \n| 144 | 328 | \n\n\n",
   "text/plain": "      [,1] [,2]\n [1,] 116  230 \n [2,] 118  234 \n [3,] 120  240 \n [4,] 122  246 \n [5,] 124  252 \n [6,] 126  258 \n [7,] 128  264 \n [8,] 130  270 \n [9,] 132  278 \n[10,] 134  284 \n[11,] 136  292 \n[12,] 138  300 \n[13,] 140  308 \n[14,] 142  318 \n[15,] 144  328 "
  },
  "metadata": {},
  "output_type": "display_data"
 },
 {
  "data": {
   "text/html": "<ol class=list-inline>\n\t<li>4.83333333333333</li>\n\t<li>4.91666666666667</li>\n\t<li>5</li>\n\t<li>5.08333333333333</li>\n\t<li>5.16666666666667</li>\n\t<li>5.25</li>\n\t<li>5.33333333333333</li>\n\t<li>5.41666666666667</li>\n\t<li>5.5</li>\n\t<li>5.58333333333333</li>\n\t<li>5.66666666666667</li>\n\t<li>5.75</li>\n\t<li>5.83333333333333</li>\n\t<li>5.91666666666667</li>\n\t<li>6</li>\n</ol>\n",
   "text/latex": "\\begin{enumerate*}\n\\item 4.83333333333333\n\\item 4.91666666666667\n\\item 5\n\\item 5.08333333333333\n\\item 5.16666666666667\n\\item 5.25\n\\item 5.33333333333333\n\\item 5.41666666666667\n\\item 5.5\n\\item 5.58333333333333\n\\item 5.66666666666667\n\\item 5.75\n\\item 5.83333333333333\n\\item 5.91666666666667\n\\item 6\n\\end{enumerate*}\n",
   "text/markdown": "1. 4.83333333333333\n2. 4.91666666666667\n3. 5\n4. 5.08333333333333\n5. 5.16666666666667\n6. 5.25\n7. 5.33333333333333\n8. 5.41666666666667\n9. 5.5\n10. 5.58333333333333\n11. 5.66666666666667\n12. 5.75\n13. 5.83333333333333\n14. 5.91666666666667\n15. 6\n\n\n",
   "text/plain": " [1] 4.833333 4.916667 5.000000 5.083333 5.166667 5.250000 5.333333 5.416667\n [9] 5.500000 5.583333 5.666667 5.750000 5.833333 5.916667 6.000000"
  },
  "metadata": {},
  "output_type": "display_data"
 },
 {
  "data": {
   "text/html": "136.733333333333",
   "text/latex": "136.733333333333",
   "text/markdown": "136.733333333333",
   "text/plain": "[1] 136.7333"
  },
  "metadata": {},
  "output_type": "display_data"
 }
]
```

```{.python .input  n=7}
dim(htwtdata)
nrow(htwtdata)
str(htwtdata)
summary(htwtdata)

```

```{.json .output n=7}
[
 {
  "data": {
   "text/html": "<ol class=list-inline>\n\t<li>15</li>\n\t<li>2</li>\n</ol>\n",
   "text/latex": "\\begin{enumerate*}\n\\item 15\n\\item 2\n\\end{enumerate*}\n",
   "text/markdown": "1. 15\n2. 2\n\n\n",
   "text/plain": "[1] 15  2"
  },
  "metadata": {},
  "output_type": "display_data"
 },
 {
  "data": {
   "text/html": "15",
   "text/latex": "15",
   "text/markdown": "15",
   "text/plain": "[1] 15"
  },
  "metadata": {},
  "output_type": "display_data"
 },
 {
  "name": "stdout",
  "output_type": "stream",
  "text": "'data.frame':\t15 obs. of  2 variables:\n $ height: num  58 59 60 61 62 63 64 65 66 67 ...\n $ weight: num  115 117 120 123 126 129 132 135 139 142 ...\n"
 },
 {
  "data": {
   "text/plain": "     height         weight     \n Min.   :58.0   Min.   :115.0  \n 1st Qu.:61.5   1st Qu.:124.5  \n Median :65.0   Median :135.0  \n Mean   :65.0   Mean   :136.7  \n 3rd Qu.:68.5   3rd Qu.:148.0  \n Max.   :72.0   Max.   :164.0  "
  },
  "metadata": {},
  "output_type": "display_data"
 }
]
```

```{.python .input  n=8}
htwtdata[,2]*703/htwtdata[,1]^2
```

```{.json .output n=8}
[
 {
  "data": {
   "text/html": "<ol class=list-inline>\n\t<li>24.032401902497</li>\n\t<li>23.6285550129273</li>\n\t<li>23.4333333333333</li>\n\t<li>23.2381080354743</li>\n\t<li>23.0431841831426</li>\n\t<li>22.848828420257</li>\n\t<li>22.6552734375</li>\n\t<li>22.4627218934911</li>\n\t<li>22.4327364554637</li>\n\t<li>22.2379149030965</li>\n\t<li>22.1967993079585</li>\n\t<li>22.1487082545684</li>\n\t<li>22.0942857142857</li>\n\t<li>22.1735766712954</li>\n\t<li>22.2399691358025</li>\n</ol>\n",
   "text/latex": "\\begin{enumerate*}\n\\item 24.032401902497\n\\item 23.6285550129273\n\\item 23.4333333333333\n\\item 23.2381080354743\n\\item 23.0431841831426\n\\item 22.848828420257\n\\item 22.6552734375\n\\item 22.4627218934911\n\\item 22.4327364554637\n\\item 22.2379149030965\n\\item 22.1967993079585\n\\item 22.1487082545684\n\\item 22.0942857142857\n\\item 22.1735766712954\n\\item 22.2399691358025\n\\end{enumerate*}\n",
   "text/markdown": "1. 24.032401902497\n2. 23.6285550129273\n3. 23.4333333333333\n4. 23.2381080354743\n5. 23.0431841831426\n6. 22.848828420257\n7. 22.6552734375\n8. 22.4627218934911\n9. 22.4327364554637\n10. 22.2379149030965\n11. 22.1967993079585\n12. 22.1487082545684\n13. 22.0942857142857\n14. 22.1735766712954\n15. 22.2399691358025\n\n\n",
   "text/plain": " [1] 24.03240 23.62856 23.43333 23.23811 23.04318 22.84883 22.65527 22.46272\n [9] 22.43274 22.23791 22.19680 22.14871 22.09429 22.17358 22.23997"
  },
  "metadata": {},
  "output_type": "display_data"
 }
]
```

```{.python .input  n=9}
# How would you get R to give you the height and weight of the 8th student in the
# data set? The 8th and 10th student?
names(htwtdata)
htwtdata[8,1]  # 8th student height
htwtdata[8,2]  #1 0th student height
htwtdata[10,1]  # 10th student height 
htwtdata[10,2]  # 10th student weight
head(htwtdata,10)         #check with head command
```

```{.json .output n=9}
[
 {
  "data": {
   "text/html": "<ol class=list-inline>\n\t<li>'height'</li>\n\t<li>'weight'</li>\n</ol>\n",
   "text/latex": "\\begin{enumerate*}\n\\item 'height'\n\\item 'weight'\n\\end{enumerate*}\n",
   "text/markdown": "1. 'height'\n2. 'weight'\n\n\n",
   "text/plain": "[1] \"height\" \"weight\""
  },
  "metadata": {},
  "output_type": "display_data"
 },
 {
  "data": {
   "text/html": "65",
   "text/latex": "65",
   "text/markdown": "65",
   "text/plain": "[1] 65"
  },
  "metadata": {},
  "output_type": "display_data"
 },
 {
  "data": {
   "text/html": "135",
   "text/latex": "135",
   "text/markdown": "135",
   "text/plain": "[1] 135"
  },
  "metadata": {},
  "output_type": "display_data"
 },
 {
  "data": {
   "text/html": "67",
   "text/latex": "67",
   "text/markdown": "67",
   "text/plain": "[1] 67"
  },
  "metadata": {},
  "output_type": "display_data"
 },
 {
  "data": {
   "text/html": "142",
   "text/latex": "142",
   "text/markdown": "142",
   "text/plain": "[1] 142"
  },
  "metadata": {},
  "output_type": "display_data"
 },
 {
  "data": {
   "text/html": "<table>\n<thead><tr><th scope=col>height</th><th scope=col>weight</th></tr></thead>\n<tbody>\n\t<tr><td>58 </td><td>115</td></tr>\n\t<tr><td>59 </td><td>117</td></tr>\n\t<tr><td>60 </td><td>120</td></tr>\n\t<tr><td>61 </td><td>123</td></tr>\n\t<tr><td>62 </td><td>126</td></tr>\n\t<tr><td>63 </td><td>129</td></tr>\n\t<tr><td>64 </td><td>132</td></tr>\n\t<tr><td>65 </td><td>135</td></tr>\n\t<tr><td>66 </td><td>139</td></tr>\n\t<tr><td>67 </td><td>142</td></tr>\n</tbody>\n</table>\n",
   "text/latex": "\\begin{tabular}{r|ll}\n height & weight\\\\\n\\hline\n\t 58  & 115\\\\\n\t 59  & 117\\\\\n\t 60  & 120\\\\\n\t 61  & 123\\\\\n\t 62  & 126\\\\\n\t 63  & 129\\\\\n\t 64  & 132\\\\\n\t 65  & 135\\\\\n\t 66  & 139\\\\\n\t 67  & 142\\\\\n\\end{tabular}\n",
   "text/markdown": "\nheight | weight | \n|---|---|---|---|---|---|---|---|---|---|\n| 58  | 115 | \n| 59  | 117 | \n| 60  | 120 | \n| 61  | 123 | \n| 62  | 126 | \n| 63  | 129 | \n| 64  | 132 | \n| 65  | 135 | \n| 66  | 139 | \n| 67  | 142 | \n\n\n",
   "text/plain": "   height weight\n1  58     115   \n2  59     117   \n3  60     120   \n4  61     123   \n5  62     126   \n6  63     129   \n7  64     132   \n8  65     135   \n9  66     139   \n10 67     142   "
  },
  "metadata": {},
  "output_type": "display_data"
 }
]
```

# Loops 
## If/else statements

In R, one can write a conditional statement as
follows:  

```R
ifelse(condition on data, true value returned, false returned)
```
    


The above expression reads: if condition on the data is true, then do
the true value assigned; otherwise execute the "false value."

```{.python .input  n=10}
ifelse(3 > 4, x <- 5, x <- 6)
print(x)

ifelse(4 > 3, x <- 5, x <- 6)
print(x)
```

```{.json .output n=10}
[
 {
  "data": {
   "text/html": "6",
   "text/latex": "6",
   "text/markdown": "6",
   "text/plain": "[1] 6"
  },
  "metadata": {},
  "output_type": "display_data"
 },
 {
  "name": "stdout",
  "output_type": "stream",
  "text": "[1] 6\n"
 },
 {
  "data": {
   "text/html": "5",
   "text/latex": "5",
   "text/markdown": "5",
   "text/plain": "[1] 5"
  },
  "metadata": {},
  "output_type": "display_data"
 },
 {
  "name": "stdout",
  "output_type": "stream",
  "text": "[1] 5\n"
 }
]
```

### Usage of operators like & & , | | , &, |

```{.python .input  n=11}
hmean =  mean(htwtdata$height)
wmean =  mean(htwtdata$weight)
?cat 
cat("mean height=",hmean,"\n","mean weight=",wmean)


```

```{.json .output n=11}
[
 {
  "name": "stdout",
  "output_type": "stream",
  "text": "mean height= 65 \n mean weight= 136.7333"
 }
]
```

The operators && and || are often used to denote multiple conditions in an if
statement. Whereas &(and) and |(or) apply element-wise to vectors, && and ||
apply to vectors of length one, and only evaluate their second argument in the
sequence if necessary. Thus it is important to remember which logical operator
to use in which situation.

```{.python .input  n=12}
ifelse( hmean > 61 && wmean > 120, x <- 5, x <- 6) # multiple conditions in an if statement
```

```{.json .output n=12}
[
 {
  "data": {
   "text/html": "5",
   "text/latex": "5",
   "text/markdown": "5",
   "text/plain": "[1] 5"
  },
  "metadata": {},
  "output_type": "display_data"
 }
]
```

```{.python .input  n=13}
htwt_cat<-ifelse (height>=70 | weight>159, "high", "low") # apply element-wise to vectors
print(htwt_cat)
is.vector(htwt_cat)

```

```{.json .output n=13}
[
 {
  "name": "stdout",
  "output_type": "stream",
  "text": " [1] \"low\"  \"low\"  \"low\"  \"low\"  \"low\"  \"low\"  \"low\"  \"low\"  \"low\"  \"low\" \n[11] \"low\"  \"low\"  \"high\" \"high\" \"high\"\n"
 },
 {
  "data": {
   "text/html": "TRUE",
   "text/latex": "TRUE",
   "text/markdown": "TRUE",
   "text/plain": "[1] TRUE"
  },
  "metadata": {},
  "output_type": "display_data"
 }
]
```

```{.python .input  n=14}
#htwtdata1<-head(htwtdata,6)
cbind(htwtdata[c(1:3,c(13:15)),],htwt_cat[c(1:3,c(13:15))])
#print(htwtdata1[1:3])
```

```{.json .output n=14}
[
 {
  "data": {
   "text/html": "<table>\n<thead><tr><th></th><th scope=col>height</th><th scope=col>weight</th><th scope=col>htwt_cat[c(1:3, c(13:15))]</th></tr></thead>\n<tbody>\n\t<tr><th scope=row>1</th><td>58  </td><td>115 </td><td>low </td></tr>\n\t<tr><th scope=row>2</th><td>59  </td><td>117 </td><td>low </td></tr>\n\t<tr><th scope=row>3</th><td>60  </td><td>120 </td><td>low </td></tr>\n\t<tr><th scope=row>13</th><td>70  </td><td>154 </td><td>high</td></tr>\n\t<tr><th scope=row>14</th><td>71  </td><td>159 </td><td>high</td></tr>\n\t<tr><th scope=row>15</th><td>72  </td><td>164 </td><td>high</td></tr>\n</tbody>\n</table>\n",
   "text/latex": "\\begin{tabular}{r|lll}\n  & height & weight & htwt\\_cat{[}c(1:3, c(13:15)){]}\\\\\n\\hline\n\t1 & 58   & 115  & low \\\\\n\t2 & 59   & 117  & low \\\\\n\t3 & 60   & 120  & low \\\\\n\t13 & 70   & 154  & high\\\\\n\t14 & 71   & 159  & high\\\\\n\t15 & 72   & 164  & high\\\\\n\\end{tabular}\n",
   "text/markdown": "\n| <!--/--> | height | weight | htwt_cat[c(1:3, c(13:15))] | \n|---|---|---|---|---|---|\n| 1 | 58   | 115  | low  | \n| 2 | 59   | 117  | low  | \n| 3 | 60   | 120  | low  | \n| 13 | 70   | 154  | high | \n| 14 | 71   | 159  | high | \n| 15 | 72   | 164  | high | \n\n\n",
   "text/plain": "   height weight htwt_cat[c(1:3, c(13:15))]\n1  58     115    low                       \n2  59     117    low                       \n3  60     120    low                       \n13 70     154    high                      \n14 71     159    high                      \n15 72     164    high                      "
  },
  "metadata": {},
  "output_type": "display_data"
 }
]
```

```{.python .input  n=15}
htwt_cat[1:6]
```

```{.json .output n=15}
[
 {
  "data": {
   "text/html": "<ol class=list-inline>\n\t<li>'low'</li>\n\t<li>'low'</li>\n\t<li>'low'</li>\n\t<li>'low'</li>\n\t<li>'low'</li>\n\t<li>'low'</li>\n</ol>\n",
   "text/latex": "\\begin{enumerate*}\n\\item 'low'\n\\item 'low'\n\\item 'low'\n\\item 'low'\n\\item 'low'\n\\item 'low'\n\\end{enumerate*}\n",
   "text/markdown": "1. 'low'\n2. 'low'\n3. 'low'\n4. 'low'\n5. 'low'\n6. 'low'\n\n\n",
   "text/plain": "[1] \"low\" \"low\" \"low\" \"low\" \"low\" \"low\""
  },
  "metadata": {},
  "output_type": "display_data"
 }
]
```

```{.python .input  n=16}
htwt_cat <- ifelse(height > 67 || weight > 150, "high", "low")
htwt_cat  
# Notice that in the above ifelse statement only the first element in the series was computed.
htwt_cat <- ifelse(height > 57 || weight > 110, "high", "low")
htwt_cat
```

```{.json .output n=16}
[
 {
  "data": {
   "text/html": "'low'",
   "text/latex": "'low'",
   "text/markdown": "'low'",
   "text/plain": "[1] \"low\""
  },
  "metadata": {},
  "output_type": "display_data"
 },
 {
  "data": {
   "text/html": "'high'",
   "text/latex": "'high'",
   "text/markdown": "'high'",
   "text/plain": "[1] \"high\""
  },
  "metadata": {},
  "output_type": "display_data"
 }
]
```

```{.python .input  n=17}
#This can also be extended to include multiple conditions.  Suppose we have the following data:

final_score<- c(39, 51, 60, 65, 72, 78, 79, 83, 85, 85, 87, 89, 91, 95, 96, 97, 100, 100)

passfail<-ifelse(final_score>=60, "pass", "fail")
passfail
```

```{.json .output n=17}
[
 {
  "data": {
   "text/html": "<ol class=list-inline>\n\t<li>'fail'</li>\n\t<li>'fail'</li>\n\t<li>'pass'</li>\n\t<li>'pass'</li>\n\t<li>'pass'</li>\n\t<li>'pass'</li>\n\t<li>'pass'</li>\n\t<li>'pass'</li>\n\t<li>'pass'</li>\n\t<li>'pass'</li>\n\t<li>'pass'</li>\n\t<li>'pass'</li>\n\t<li>'pass'</li>\n\t<li>'pass'</li>\n\t<li>'pass'</li>\n\t<li>'pass'</li>\n\t<li>'pass'</li>\n\t<li>'pass'</li>\n</ol>\n",
   "text/latex": "\\begin{enumerate*}\n\\item 'fail'\n\\item 'fail'\n\\item 'pass'\n\\item 'pass'\n\\item 'pass'\n\\item 'pass'\n\\item 'pass'\n\\item 'pass'\n\\item 'pass'\n\\item 'pass'\n\\item 'pass'\n\\item 'pass'\n\\item 'pass'\n\\item 'pass'\n\\item 'pass'\n\\item 'pass'\n\\item 'pass'\n\\item 'pass'\n\\end{enumerate*}\n",
   "text/markdown": "1. 'fail'\n2. 'fail'\n3. 'pass'\n4. 'pass'\n5. 'pass'\n6. 'pass'\n7. 'pass'\n8. 'pass'\n9. 'pass'\n10. 'pass'\n11. 'pass'\n12. 'pass'\n13. 'pass'\n14. 'pass'\n15. 'pass'\n16. 'pass'\n17. 'pass'\n18. 'pass'\n\n\n",
   "text/plain": " [1] \"fail\" \"fail\" \"pass\" \"pass\" \"pass\" \"pass\" \"pass\" \"pass\" \"pass\" \"pass\"\n[11] \"pass\" \"pass\" \"pass\" \"pass\" \"pass\" \"pass\" \"pass\" \"pass\""
  },
  "metadata": {},
  "output_type": "display_data"
 }
]
```

#Suppose we want to create a variable called grades that is assigned as follows:
```R 
"F" if final_score <60

"D" if 60≤final_score<70

"C" if 70≤final_score<80
"B" if 80≤final_score<90

"A" if 90≤final_score 
```

### Nested ifelse Statements

We can use a "nested" ifelse command as follows:

```{.python .input  n=18}
grade <- ifelse(final_score < 60, "F", ifelse(final_score < 70, "D", ifelse(final_score < 
    80, "C", ifelse(final_score < 90, "B", "A"))))

grade
```

```{.json .output n=18}
[
 {
  "data": {
   "text/html": "<ol class=list-inline>\n\t<li>'F'</li>\n\t<li>'F'</li>\n\t<li>'D'</li>\n\t<li>'D'</li>\n\t<li>'C'</li>\n\t<li>'C'</li>\n\t<li>'C'</li>\n\t<li>'B'</li>\n\t<li>'B'</li>\n\t<li>'B'</li>\n\t<li>'B'</li>\n\t<li>'B'</li>\n\t<li>'A'</li>\n\t<li>'A'</li>\n\t<li>'A'</li>\n\t<li>'A'</li>\n\t<li>'A'</li>\n\t<li>'A'</li>\n</ol>\n",
   "text/latex": "\\begin{enumerate*}\n\\item 'F'\n\\item 'F'\n\\item 'D'\n\\item 'D'\n\\item 'C'\n\\item 'C'\n\\item 'C'\n\\item 'B'\n\\item 'B'\n\\item 'B'\n\\item 'B'\n\\item 'B'\n\\item 'A'\n\\item 'A'\n\\item 'A'\n\\item 'A'\n\\item 'A'\n\\item 'A'\n\\end{enumerate*}\n",
   "text/markdown": "1. 'F'\n2. 'F'\n3. 'D'\n4. 'D'\n5. 'C'\n6. 'C'\n7. 'C'\n8. 'B'\n9. 'B'\n10. 'B'\n11. 'B'\n12. 'B'\n13. 'A'\n14. 'A'\n15. 'A'\n16. 'A'\n17. 'A'\n18. 'A'\n\n\n",
   "text/plain": " [1] \"F\" \"F\" \"D\" \"D\" \"C\" \"C\" \"C\" \"B\" \"B\" \"B\" \"B\" \"B\" \"A\" \"A\" \"A\" \"A\" \"A\" \"A\""
  },
  "metadata": {},
  "output_type": "display_data"
 }
]
```

The logic by which this will assign grades is depicted in the figure below.
![Image of
NestedIf](https://drive.google.com/uc?id=0B14DjwBCvz91d1k2a0l5X3ZHVDg)
#if we want to resize the image we can use the below code 

<a href="url"><img src="https://drive.google.com/uc?id=0B14DjwBCvz91d1k2a0l5X3ZHVDg" align="center" height="548" width="348" ></a>
### Repetitive Execution: "for" loops, "repeat" and "while"

syntax of for loop
is:  
```R
for (name in expr_1) expr_2
```
here name is the loop variable,
expr_1 is a vector expression, (often a sequence like 1:20), and expr_2 is often
a grouped expression with its sub-expressions written in terms of the dummy
name. expr_2 is repeatedly evaluated as name ranges through the values in the
vector result of expr_1.

```{.python .input  n=19}
# let's take airquality dataset which is the Daily air quality measurements in
# New York, May to September 1973. for the details use 
?airquality
```

```{.python .input  n=20}
# we want to figure out which days were good air quality days (1) or bad air
# quality (0), based on a cutoff of ozone levels above 60ppb.
numdays <- nrow(airquality)
print(numdays)
```

```{.json .output n=20}
[
 {
  "name": "stdout",
  "output_type": "stream",
  "text": "[1] 153\n"
 }
]
```

```{.python .input  n=21}
# creates an object which will store the vector
goodair <- numeric(numdays)
print(goodair)
```

```{.json .output n=21}
[
 {
  "name": "stdout",
  "output_type": "stream",
  "text": "  [1] 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0\n [38] 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0\n [75] 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0\n[112] 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0\n[149] 0 0 0 0 0\n"
 }
]
```

```R
for(i in 1:numdays)
    if (airquality$Ozone[i] > 60) goodair[i] = 0 else
goodair[i] = 1
        ```
##(Notice that we have an if statement here within a
for loop.)

```{.python .input  n=22}
#Does the command above work? Why/why not?
#Let's check the Ozone variable. What do you notice below?
airquality$Ozone
```

```{.json .output n=22}
[
 {
  "data": {
   "text/html": "<ol class=list-inline>\n\t<li>41</li>\n\t<li>36</li>\n\t<li>12</li>\n\t<li>18</li>\n\t<li>NA</li>\n\t<li>28</li>\n\t<li>23</li>\n\t<li>19</li>\n\t<li>8</li>\n\t<li>NA</li>\n\t<li>7</li>\n\t<li>16</li>\n\t<li>11</li>\n\t<li>14</li>\n\t<li>18</li>\n\t<li>14</li>\n\t<li>34</li>\n\t<li>6</li>\n\t<li>30</li>\n\t<li>11</li>\n\t<li>1</li>\n\t<li>11</li>\n\t<li>4</li>\n\t<li>32</li>\n\t<li>NA</li>\n\t<li>NA</li>\n\t<li>NA</li>\n\t<li>23</li>\n\t<li>45</li>\n\t<li>115</li>\n\t<li>37</li>\n\t<li>NA</li>\n\t<li>NA</li>\n\t<li>NA</li>\n\t<li>NA</li>\n\t<li>NA</li>\n\t<li>NA</li>\n\t<li>29</li>\n\t<li>NA</li>\n\t<li>71</li>\n\t<li>39</li>\n\t<li>NA</li>\n\t<li>NA</li>\n\t<li>23</li>\n\t<li>NA</li>\n\t<li>NA</li>\n\t<li>21</li>\n\t<li>37</li>\n\t<li>20</li>\n\t<li>12</li>\n\t<li>13</li>\n\t<li>NA</li>\n\t<li>NA</li>\n\t<li>NA</li>\n\t<li>NA</li>\n\t<li>NA</li>\n\t<li>NA</li>\n\t<li>NA</li>\n\t<li>NA</li>\n\t<li>NA</li>\n\t<li>NA</li>\n\t<li>135</li>\n\t<li>49</li>\n\t<li>32</li>\n\t<li>NA</li>\n\t<li>64</li>\n\t<li>40</li>\n\t<li>77</li>\n\t<li>97</li>\n\t<li>97</li>\n\t<li>85</li>\n\t<li>NA</li>\n\t<li>10</li>\n\t<li>27</li>\n\t<li>NA</li>\n\t<li>7</li>\n\t<li>48</li>\n\t<li>35</li>\n\t<li>61</li>\n\t<li>79</li>\n\t<li>63</li>\n\t<li>16</li>\n\t<li>NA</li>\n\t<li>NA</li>\n\t<li>80</li>\n\t<li>108</li>\n\t<li>20</li>\n\t<li>52</li>\n\t<li>82</li>\n\t<li>50</li>\n\t<li>64</li>\n\t<li>59</li>\n\t<li>39</li>\n\t<li>9</li>\n\t<li>16</li>\n\t<li>78</li>\n\t<li>35</li>\n\t<li>66</li>\n\t<li>122</li>\n\t<li>89</li>\n\t<li>110</li>\n\t<li>NA</li>\n\t<li>NA</li>\n\t<li>44</li>\n\t<li>28</li>\n\t<li>65</li>\n\t<li>NA</li>\n\t<li>22</li>\n\t<li>59</li>\n\t<li>23</li>\n\t<li>31</li>\n\t<li>44</li>\n\t<li>21</li>\n\t<li>9</li>\n\t<li>NA</li>\n\t<li>45</li>\n\t<li>168</li>\n\t<li>73</li>\n\t<li>NA</li>\n\t<li>76</li>\n\t<li>118</li>\n\t<li>84</li>\n\t<li>85</li>\n\t<li>96</li>\n\t<li>78</li>\n\t<li>73</li>\n\t<li>91</li>\n\t<li>47</li>\n\t<li>32</li>\n\t<li>20</li>\n\t<li>23</li>\n\t<li>21</li>\n\t<li>24</li>\n\t<li>44</li>\n\t<li>21</li>\n\t<li>28</li>\n\t<li>9</li>\n\t<li>13</li>\n\t<li>46</li>\n\t<li>18</li>\n\t<li>13</li>\n\t<li>24</li>\n\t<li>16</li>\n\t<li>13</li>\n\t<li>23</li>\n\t<li>36</li>\n\t<li>7</li>\n\t<li>14</li>\n\t<li>30</li>\n\t<li>NA</li>\n\t<li>14</li>\n\t<li>18</li>\n\t<li>20</li>\n</ol>\n",
   "text/latex": "\\begin{enumerate*}\n\\item 41\n\\item 36\n\\item 12\n\\item 18\n\\item NA\n\\item 28\n\\item 23\n\\item 19\n\\item 8\n\\item NA\n\\item 7\n\\item 16\n\\item 11\n\\item 14\n\\item 18\n\\item 14\n\\item 34\n\\item 6\n\\item 30\n\\item 11\n\\item 1\n\\item 11\n\\item 4\n\\item 32\n\\item NA\n\\item NA\n\\item NA\n\\item 23\n\\item 45\n\\item 115\n\\item 37\n\\item NA\n\\item NA\n\\item NA\n\\item NA\n\\item NA\n\\item NA\n\\item 29\n\\item NA\n\\item 71\n\\item 39\n\\item NA\n\\item NA\n\\item 23\n\\item NA\n\\item NA\n\\item 21\n\\item 37\n\\item 20\n\\item 12\n\\item 13\n\\item NA\n\\item NA\n\\item NA\n\\item NA\n\\item NA\n\\item NA\n\\item NA\n\\item NA\n\\item NA\n\\item NA\n\\item 135\n\\item 49\n\\item 32\n\\item NA\n\\item 64\n\\item 40\n\\item 77\n\\item 97\n\\item 97\n\\item 85\n\\item NA\n\\item 10\n\\item 27\n\\item NA\n\\item 7\n\\item 48\n\\item 35\n\\item 61\n\\item 79\n\\item 63\n\\item 16\n\\item NA\n\\item NA\n\\item 80\n\\item 108\n\\item 20\n\\item 52\n\\item 82\n\\item 50\n\\item 64\n\\item 59\n\\item 39\n\\item 9\n\\item 16\n\\item 78\n\\item 35\n\\item 66\n\\item 122\n\\item 89\n\\item 110\n\\item NA\n\\item NA\n\\item 44\n\\item 28\n\\item 65\n\\item NA\n\\item 22\n\\item 59\n\\item 23\n\\item 31\n\\item 44\n\\item 21\n\\item 9\n\\item NA\n\\item 45\n\\item 168\n\\item 73\n\\item NA\n\\item 76\n\\item 118\n\\item 84\n\\item 85\n\\item 96\n\\item 78\n\\item 73\n\\item 91\n\\item 47\n\\item 32\n\\item 20\n\\item 23\n\\item 21\n\\item 24\n\\item 44\n\\item 21\n\\item 28\n\\item 9\n\\item 13\n\\item 46\n\\item 18\n\\item 13\n\\item 24\n\\item 16\n\\item 13\n\\item 23\n\\item 36\n\\item 7\n\\item 14\n\\item 30\n\\item NA\n\\item 14\n\\item 18\n\\item 20\n\\end{enumerate*}\n",
   "text/markdown": "1. 41\n2. 36\n3. 12\n4. 18\n5. NA\n6. 28\n7. 23\n8. 19\n9. 8\n10. NA\n11. 7\n12. 16\n13. 11\n14. 14\n15. 18\n16. 14\n17. 34\n18. 6\n19. 30\n20. 11\n21. 1\n22. 11\n23. 4\n24. 32\n25. NA\n26. NA\n27. NA\n28. 23\n29. 45\n30. 115\n31. 37\n32. NA\n33. NA\n34. NA\n35. NA\n36. NA\n37. NA\n38. 29\n39. NA\n40. 71\n41. 39\n42. NA\n43. NA\n44. 23\n45. NA\n46. NA\n47. 21\n48. 37\n49. 20\n50. 12\n51. 13\n52. NA\n53. NA\n54. NA\n55. NA\n56. NA\n57. NA\n58. NA\n59. NA\n60. NA\n61. NA\n62. 135\n63. 49\n64. 32\n65. NA\n66. 64\n67. 40\n68. 77\n69. 97\n70. 97\n71. 85\n72. NA\n73. 10\n74. 27\n75. NA\n76. 7\n77. 48\n78. 35\n79. 61\n80. 79\n81. 63\n82. 16\n83. NA\n84. NA\n85. 80\n86. 108\n87. 20\n88. 52\n89. 82\n90. 50\n91. 64\n92. 59\n93. 39\n94. 9\n95. 16\n96. 78\n97. 35\n98. 66\n99. 122\n100. 89\n101. 110\n102. NA\n103. NA\n104. 44\n105. 28\n106. 65\n107. NA\n108. 22\n109. 59\n110. 23\n111. 31\n112. 44\n113. 21\n114. 9\n115. NA\n116. 45\n117. 168\n118. 73\n119. NA\n120. 76\n121. 118\n122. 84\n123. 85\n124. 96\n125. 78\n126. 73\n127. 91\n128. 47\n129. 32\n130. 20\n131. 23\n132. 21\n133. 24\n134. 44\n135. 21\n136. 28\n137. 9\n138. 13\n139. 46\n140. 18\n141. 13\n142. 24\n143. 16\n144. 13\n145. 23\n146. 36\n147. 7\n148. 14\n149. 30\n150. NA\n151. 14\n152. 18\n153. 20\n\n\n",
   "text/plain": "  [1]  41  36  12  18  NA  28  23  19   8  NA   7  16  11  14  18  14  34   6\n [19]  30  11   1  11   4  32  NA  NA  NA  23  45 115  37  NA  NA  NA  NA  NA\n [37]  NA  29  NA  71  39  NA  NA  23  NA  NA  21  37  20  12  13  NA  NA  NA\n [55]  NA  NA  NA  NA  NA  NA  NA 135  49  32  NA  64  40  77  97  97  85  NA\n [73]  10  27  NA   7  48  35  61  79  63  16  NA  NA  80 108  20  52  82  50\n [91]  64  59  39   9  16  78  35  66 122  89 110  NA  NA  44  28  65  NA  22\n[109]  59  23  31  44  21   9  NA  45 168  73  NA  76 118  84  85  96  78  73\n[127]  91  47  32  20  23  21  24  44  21  28   9  13  46  18  13  24  16  13\n[145]  23  36   7  14  30  NA  14  18  20"
  },
  "metadata": {},
  "output_type": "display_data"
 }
]
```

```{.python .input  n=23}
# When there are missing values, many operations in R fail. One way to get around
# this is to create a new data frame that deletes all the rows corresponding to
# observations with missing rows. This can be done by means of the command
# 'na.omit'
airqualfull = na.omit(airquality)
```

```{.python .input  n=24}
dim(airqualfull)
dim(airquality)  
```

```{.json .output n=24}
[
 {
  "data": {
   "text/html": "<ol class=list-inline>\n\t<li>111</li>\n\t<li>6</li>\n</ol>\n",
   "text/latex": "\\begin{enumerate*}\n\\item 111\n\\item 6\n\\end{enumerate*}\n",
   "text/markdown": "1. 111\n2. 6\n\n\n",
   "text/plain": "[1] 111   6"
  },
  "metadata": {},
  "output_type": "display_data"
 },
 {
  "data": {
   "text/html": "<ol class=list-inline>\n\t<li>153</li>\n\t<li>6</li>\n</ol>\n",
   "text/latex": "\\begin{enumerate*}\n\\item 153\n\\item 6\n\\end{enumerate*}\n",
   "text/markdown": "1. 153\n2. 6\n\n\n",
   "text/plain": "[1] 153   6"
  },
  "metadata": {},
  "output_type": "display_data"
 }
]
```

```{.python .input  n=25}
#Now let's try doing this again with the data with the complete cases.
numdays = nrow(airqualfull)
numdays
print(numdays)

```

```{.json .output n=25}
[
 {
  "data": {
   "text/html": "111",
   "text/latex": "111",
   "text/markdown": "111",
   "text/plain": "[1] 111"
  },
  "metadata": {},
  "output_type": "display_data"
 },
 {
  "name": "stdout",
  "output_type": "stream",
  "text": "[1] 111\n"
 }
]
```

```{.python .input  n=26}
goodair = numeric(numdays)       # initialize the vector
```

```{.python .input  n=27}
for(i in 1:numdays)

    if (airqualfull$Ozone[i] >60) goodair[i] = 0 else goodair[i] = 1
```

```{.python .input  n=28}
goodair
```

```{.json .output n=28}
[
 {
  "data": {
   "text/html": "<ol class=list-inline>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>0</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>0</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>0</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>0</li>\n\t<li>1</li>\n\t<li>0</li>\n\t<li>0</li>\n\t<li>0</li>\n\t<li>0</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>0</li>\n\t<li>0</li>\n\t<li>0</li>\n\t<li>1</li>\n\t<li>0</li>\n\t<li>0</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>0</li>\n\t<li>1</li>\n\t<li>0</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>0</li>\n\t<li>0</li>\n\t<li>0</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>0</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>0</li>\n\t<li>0</li>\n\t<li>0</li>\n\t<li>0</li>\n\t<li>0</li>\n\t<li>0</li>\n\t<li>0</li>\n\t<li>0</li>\n\t<li>0</li>\n\t<li>0</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>1</li>\n\t<li>1</li>\n</ol>\n",
   "text/latex": "\\begin{enumerate*}\n\\item 1\n\\item 1\n\\item 1\n\\item 1\n\\item 1\n\\item 1\n\\item 1\n\\item 1\n\\item 1\n\\item 1\n\\item 1\n\\item 1\n\\item 1\n\\item 1\n\\item 1\n\\item 1\n\\item 1\n\\item 1\n\\item 1\n\\item 1\n\\item 1\n\\item 1\n\\item 0\n\\item 1\n\\item 1\n\\item 0\n\\item 1\n\\item 1\n\\item 1\n\\item 1\n\\item 1\n\\item 1\n\\item 1\n\\item 0\n\\item 1\n\\item 1\n\\item 0\n\\item 1\n\\item 0\n\\item 0\n\\item 0\n\\item 0\n\\item 1\n\\item 1\n\\item 1\n\\item 1\n\\item 1\n\\item 0\n\\item 0\n\\item 0\n\\item 1\n\\item 0\n\\item 0\n\\item 1\n\\item 1\n\\item 0\n\\item 1\n\\item 0\n\\item 1\n\\item 1\n\\item 1\n\\item 1\n\\item 0\n\\item 0\n\\item 0\n\\item 1\n\\item 1\n\\item 0\n\\item 1\n\\item 1\n\\item 1\n\\item 1\n\\item 1\n\\item 1\n\\item 1\n\\item 1\n\\item 0\n\\item 0\n\\item 0\n\\item 0\n\\item 0\n\\item 0\n\\item 0\n\\item 0\n\\item 0\n\\item 0\n\\item 1\n\\item 1\n\\item 1\n\\item 1\n\\item 1\n\\item 1\n\\item 1\n\\item 1\n\\item 1\n\\item 1\n\\item 1\n\\item 1\n\\item 1\n\\item 1\n\\item 1\n\\item 1\n\\item 1\n\\item 1\n\\item 1\n\\item 1\n\\item 1\n\\item 1\n\\item 1\n\\item 1\n\\item 1\n\\end{enumerate*}\n",
   "text/markdown": "1. 1\n2. 1\n3. 1\n4. 1\n5. 1\n6. 1\n7. 1\n8. 1\n9. 1\n10. 1\n11. 1\n12. 1\n13. 1\n14. 1\n15. 1\n16. 1\n17. 1\n18. 1\n19. 1\n20. 1\n21. 1\n22. 1\n23. 0\n24. 1\n25. 1\n26. 0\n27. 1\n28. 1\n29. 1\n30. 1\n31. 1\n32. 1\n33. 1\n34. 0\n35. 1\n36. 1\n37. 0\n38. 1\n39. 0\n40. 0\n41. 0\n42. 0\n43. 1\n44. 1\n45. 1\n46. 1\n47. 1\n48. 0\n49. 0\n50. 0\n51. 1\n52. 0\n53. 0\n54. 1\n55. 1\n56. 0\n57. 1\n58. 0\n59. 1\n60. 1\n61. 1\n62. 1\n63. 0\n64. 0\n65. 0\n66. 1\n67. 1\n68. 0\n69. 1\n70. 1\n71. 1\n72. 1\n73. 1\n74. 1\n75. 1\n76. 1\n77. 0\n78. 0\n79. 0\n80. 0\n81. 0\n82. 0\n83. 0\n84. 0\n85. 0\n86. 0\n87. 1\n88. 1\n89. 1\n90. 1\n91. 1\n92. 1\n93. 1\n94. 1\n95. 1\n96. 1\n97. 1\n98. 1\n99. 1\n100. 1\n101. 1\n102. 1\n103. 1\n104. 1\n105. 1\n106. 1\n107. 1\n108. 1\n109. 1\n110. 1\n111. 1\n\n\n",
   "text/plain": "  [1] 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 0 1 1 0 1 1 1 1 1 1 1 0 1 1 0\n [38] 1 0 0 0 0 1 1 1 1 1 0 0 0 1 0 0 1 1 0 1 0 1 1 1 1 0 0 0 1 1 0 1 1 1 1 1 1\n [75] 1 1 0 0 0 0 0 0 0 0 0 0 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1"
  },
  "metadata": {},
  "output_type": "display_data"
 }
]
```

```{.python .input  n=29}
# At this point we might be interested in which days were the ones with good air
# quality. The 'which' command returns a set of indices corresponding to the
# condition specified. We can then use the indices to find the day of the month
# this corresponds to
which(goodair == 1)    ## notice the double "=" signs!
```

```{.json .output n=29}
[
 {
  "data": {
   "text/html": "<ol class=list-inline>\n\t<li>1</li>\n\t<li>2</li>\n\t<li>3</li>\n\t<li>4</li>\n\t<li>5</li>\n\t<li>6</li>\n\t<li>7</li>\n\t<li>8</li>\n\t<li>9</li>\n\t<li>10</li>\n\t<li>11</li>\n\t<li>12</li>\n\t<li>13</li>\n\t<li>14</li>\n\t<li>15</li>\n\t<li>16</li>\n\t<li>17</li>\n\t<li>18</li>\n\t<li>19</li>\n\t<li>20</li>\n\t<li>21</li>\n\t<li>22</li>\n\t<li>24</li>\n\t<li>25</li>\n\t<li>27</li>\n\t<li>28</li>\n\t<li>29</li>\n\t<li>30</li>\n\t<li>31</li>\n\t<li>32</li>\n\t<li>33</li>\n\t<li>35</li>\n\t<li>36</li>\n\t<li>38</li>\n\t<li>43</li>\n\t<li>44</li>\n\t<li>45</li>\n\t<li>46</li>\n\t<li>47</li>\n\t<li>51</li>\n\t<li>54</li>\n\t<li>55</li>\n\t<li>57</li>\n\t<li>59</li>\n\t<li>60</li>\n\t<li>61</li>\n\t<li>62</li>\n\t<li>66</li>\n\t<li>67</li>\n\t<li>69</li>\n\t<li>70</li>\n\t<li>71</li>\n\t<li>72</li>\n\t<li>73</li>\n\t<li>74</li>\n\t<li>75</li>\n\t<li>76</li>\n\t<li>87</li>\n\t<li>88</li>\n\t<li>89</li>\n\t<li>90</li>\n\t<li>91</li>\n\t<li>92</li>\n\t<li>93</li>\n\t<li>94</li>\n\t<li>95</li>\n\t<li>96</li>\n\t<li>97</li>\n\t<li>98</li>\n\t<li>99</li>\n\t<li>100</li>\n\t<li>101</li>\n\t<li>102</li>\n\t<li>103</li>\n\t<li>104</li>\n\t<li>105</li>\n\t<li>106</li>\n\t<li>107</li>\n\t<li>108</li>\n\t<li>109</li>\n\t<li>110</li>\n\t<li>111</li>\n</ol>\n",
   "text/latex": "\\begin{enumerate*}\n\\item 1\n\\item 2\n\\item 3\n\\item 4\n\\item 5\n\\item 6\n\\item 7\n\\item 8\n\\item 9\n\\item 10\n\\item 11\n\\item 12\n\\item 13\n\\item 14\n\\item 15\n\\item 16\n\\item 17\n\\item 18\n\\item 19\n\\item 20\n\\item 21\n\\item 22\n\\item 24\n\\item 25\n\\item 27\n\\item 28\n\\item 29\n\\item 30\n\\item 31\n\\item 32\n\\item 33\n\\item 35\n\\item 36\n\\item 38\n\\item 43\n\\item 44\n\\item 45\n\\item 46\n\\item 47\n\\item 51\n\\item 54\n\\item 55\n\\item 57\n\\item 59\n\\item 60\n\\item 61\n\\item 62\n\\item 66\n\\item 67\n\\item 69\n\\item 70\n\\item 71\n\\item 72\n\\item 73\n\\item 74\n\\item 75\n\\item 76\n\\item 87\n\\item 88\n\\item 89\n\\item 90\n\\item 91\n\\item 92\n\\item 93\n\\item 94\n\\item 95\n\\item 96\n\\item 97\n\\item 98\n\\item 99\n\\item 100\n\\item 101\n\\item 102\n\\item 103\n\\item 104\n\\item 105\n\\item 106\n\\item 107\n\\item 108\n\\item 109\n\\item 110\n\\item 111\n\\end{enumerate*}\n",
   "text/markdown": "1. 1\n2. 2\n3. 3\n4. 4\n5. 5\n6. 6\n7. 7\n8. 8\n9. 9\n10. 10\n11. 11\n12. 12\n13. 13\n14. 14\n15. 15\n16. 16\n17. 17\n18. 18\n19. 19\n20. 20\n21. 21\n22. 22\n23. 24\n24. 25\n25. 27\n26. 28\n27. 29\n28. 30\n29. 31\n30. 32\n31. 33\n32. 35\n33. 36\n34. 38\n35. 43\n36. 44\n37. 45\n38. 46\n39. 47\n40. 51\n41. 54\n42. 55\n43. 57\n44. 59\n45. 60\n46. 61\n47. 62\n48. 66\n49. 67\n50. 69\n51. 70\n52. 71\n53. 72\n54. 73\n55. 74\n56. 75\n57. 76\n58. 87\n59. 88\n60. 89\n61. 90\n62. 91\n63. 92\n64. 93\n65. 94\n66. 95\n67. 96\n68. 97\n69. 98\n70. 99\n71. 100\n72. 101\n73. 102\n74. 103\n75. 104\n76. 105\n77. 106\n78. 107\n79. 108\n80. 109\n81. 110\n82. 111\n\n\n",
   "text/plain": " [1]   1   2   3   4   5   6   7   8   9  10  11  12  13  14  15  16  17  18  19\n[20]  20  21  22  24  25  27  28  29  30  31  32  33  35  36  38  43  44  45  46\n[39]  47  51  54  55  57  59  60  61  62  66  67  69  70  71  72  73  74  75  76\n[58]  87  88  89  90  91  92  93  94  95  96  97  98  99 100 101 102 103 104 105\n[77] 106 107 108 109 110 111"
  },
  "metadata": {},
  "output_type": "display_data"
 }
]
```

```{.python .input  n=30}
goodindices <-  which(goodair == 1)
airqualfull[goodindices,] 
```

```{.json .output n=30}
[
 {
  "data": {
   "text/html": "<table>\n<thead><tr><th></th><th scope=col>Ozone</th><th scope=col>Solar.R</th><th scope=col>Wind</th><th scope=col>Temp</th><th scope=col>Month</th><th scope=col>Day</th></tr></thead>\n<tbody>\n\t<tr><th scope=row>1</th><td>41  </td><td>190 </td><td> 7.4</td><td>67  </td><td>5   </td><td> 1  </td></tr>\n\t<tr><th scope=row>2</th><td>36  </td><td>118 </td><td> 8.0</td><td>72  </td><td>5   </td><td> 2  </td></tr>\n\t<tr><th scope=row>3</th><td>12  </td><td>149 </td><td>12.6</td><td>74  </td><td>5   </td><td> 3  </td></tr>\n\t<tr><th scope=row>4</th><td>18  </td><td>313 </td><td>11.5</td><td>62  </td><td>5   </td><td> 4  </td></tr>\n\t<tr><th scope=row>7</th><td>23  </td><td>299 </td><td> 8.6</td><td>65  </td><td>5   </td><td> 7  </td></tr>\n\t<tr><th scope=row>8</th><td>19  </td><td> 99 </td><td>13.8</td><td>59  </td><td>5   </td><td> 8  </td></tr>\n\t<tr><th scope=row>9</th><td> 8  </td><td> 19 </td><td>20.1</td><td>61  </td><td>5   </td><td> 9  </td></tr>\n\t<tr><th scope=row>12</th><td>16  </td><td>256 </td><td> 9.7</td><td>69  </td><td>5   </td><td>12  </td></tr>\n\t<tr><th scope=row>13</th><td>11  </td><td>290 </td><td> 9.2</td><td>66  </td><td>5   </td><td>13  </td></tr>\n\t<tr><th scope=row>14</th><td>14  </td><td>274 </td><td>10.9</td><td>68  </td><td>5   </td><td>14  </td></tr>\n\t<tr><th scope=row>15</th><td>18  </td><td> 65 </td><td>13.2</td><td>58  </td><td>5   </td><td>15  </td></tr>\n\t<tr><th scope=row>16</th><td>14  </td><td>334 </td><td>11.5</td><td>64  </td><td>5   </td><td>16  </td></tr>\n\t<tr><th scope=row>17</th><td>34  </td><td>307 </td><td>12.0</td><td>66  </td><td>5   </td><td>17  </td></tr>\n\t<tr><th scope=row>18</th><td> 6  </td><td> 78 </td><td>18.4</td><td>57  </td><td>5   </td><td>18  </td></tr>\n\t<tr><th scope=row>19</th><td>30  </td><td>322 </td><td>11.5</td><td>68  </td><td>5   </td><td>19  </td></tr>\n\t<tr><th scope=row>20</th><td>11  </td><td> 44 </td><td> 9.7</td><td>62  </td><td>5   </td><td>20  </td></tr>\n\t<tr><th scope=row>21</th><td> 1  </td><td>  8 </td><td> 9.7</td><td>59  </td><td>5   </td><td>21  </td></tr>\n\t<tr><th scope=row>22</th><td>11  </td><td>320 </td><td>16.6</td><td>73  </td><td>5   </td><td>22  </td></tr>\n\t<tr><th scope=row>23</th><td> 4  </td><td> 25 </td><td> 9.7</td><td>61  </td><td>5   </td><td>23  </td></tr>\n\t<tr><th scope=row>24</th><td>32  </td><td> 92 </td><td>12.0</td><td>61  </td><td>5   </td><td>24  </td></tr>\n\t<tr><th scope=row>28</th><td>23  </td><td> 13 </td><td>12.0</td><td>67  </td><td>5   </td><td>28  </td></tr>\n\t<tr><th scope=row>29</th><td>45  </td><td>252 </td><td>14.9</td><td>81  </td><td>5   </td><td>29  </td></tr>\n\t<tr><th scope=row>31</th><td>37  </td><td>279 </td><td> 7.4</td><td>76  </td><td>5   </td><td>31  </td></tr>\n\t<tr><th scope=row>38</th><td>29  </td><td>127 </td><td> 9.7</td><td>82  </td><td>6   </td><td> 7  </td></tr>\n\t<tr><th scope=row>41</th><td>39  </td><td>323 </td><td>11.5</td><td>87  </td><td>6   </td><td>10  </td></tr>\n\t<tr><th scope=row>44</th><td>23  </td><td>148 </td><td> 8.0</td><td>82  </td><td>6   </td><td>13  </td></tr>\n\t<tr><th scope=row>47</th><td>21  </td><td>191 </td><td>14.9</td><td>77  </td><td>6   </td><td>16  </td></tr>\n\t<tr><th scope=row>48</th><td>37  </td><td>284 </td><td>20.7</td><td>72  </td><td>6   </td><td>17  </td></tr>\n\t<tr><th scope=row>49</th><td>20  </td><td> 37 </td><td> 9.2</td><td>65  </td><td>6   </td><td>18  </td></tr>\n\t<tr><th scope=row>50</th><td>12  </td><td>120 </td><td>11.5</td><td>73  </td><td>6   </td><td>19  </td></tr>\n\t<tr><th scope=row>...</th><td>...</td><td>...</td><td>...</td><td>...</td><td>...</td><td>...</td></tr>\n\t<tr><th scope=row>111</th><td>31  </td><td>244 </td><td>10.9</td><td>78  </td><td>8   </td><td>19  </td></tr>\n\t<tr><th scope=row>112</th><td>44  </td><td>190 </td><td>10.3</td><td>78  </td><td>8   </td><td>20  </td></tr>\n\t<tr><th scope=row>113</th><td>21  </td><td>259 </td><td>15.5</td><td>77  </td><td>8   </td><td>21  </td></tr>\n\t<tr><th scope=row>114</th><td> 9  </td><td> 36 </td><td>14.3</td><td>72  </td><td>8   </td><td>22  </td></tr>\n\t<tr><th scope=row>116</th><td>45  </td><td>212 </td><td> 9.7</td><td>79  </td><td>8   </td><td>24  </td></tr>\n\t<tr><th scope=row>128</th><td>47  </td><td> 95 </td><td> 7.4</td><td>87  </td><td>9   </td><td> 5  </td></tr>\n\t<tr><th scope=row>129</th><td>32  </td><td> 92 </td><td>15.5</td><td>84  </td><td>9   </td><td> 6  </td></tr>\n\t<tr><th scope=row>130</th><td>20  </td><td>252 </td><td>10.9</td><td>80  </td><td>9   </td><td> 7  </td></tr>\n\t<tr><th scope=row>131</th><td>23  </td><td>220 </td><td>10.3</td><td>78  </td><td>9   </td><td> 8  </td></tr>\n\t<tr><th scope=row>132</th><td>21  </td><td>230 </td><td>10.9</td><td>75  </td><td>9   </td><td> 9  </td></tr>\n\t<tr><th scope=row>133</th><td>24  </td><td>259 </td><td> 9.7</td><td>73  </td><td>9   </td><td>10  </td></tr>\n\t<tr><th scope=row>134</th><td>44  </td><td>236 </td><td>14.9</td><td>81  </td><td>9   </td><td>11  </td></tr>\n\t<tr><th scope=row>135</th><td>21  </td><td>259 </td><td>15.5</td><td>76  </td><td>9   </td><td>12  </td></tr>\n\t<tr><th scope=row>136</th><td>28  </td><td>238 </td><td> 6.3</td><td>77  </td><td>9   </td><td>13  </td></tr>\n\t<tr><th scope=row>137</th><td> 9  </td><td> 24 </td><td>10.9</td><td>71  </td><td>9   </td><td>14  </td></tr>\n\t<tr><th scope=row>138</th><td>13  </td><td>112 </td><td>11.5</td><td>71  </td><td>9   </td><td>15  </td></tr>\n\t<tr><th scope=row>139</th><td>46  </td><td>237 </td><td> 6.9</td><td>78  </td><td>9   </td><td>16  </td></tr>\n\t<tr><th scope=row>140</th><td>18  </td><td>224 </td><td>13.8</td><td>67  </td><td>9   </td><td>17  </td></tr>\n\t<tr><th scope=row>141</th><td>13  </td><td> 27 </td><td>10.3</td><td>76  </td><td>9   </td><td>18  </td></tr>\n\t<tr><th scope=row>142</th><td>24  </td><td>238 </td><td>10.3</td><td>68  </td><td>9   </td><td>19  </td></tr>\n\t<tr><th scope=row>143</th><td>16  </td><td>201 </td><td> 8.0</td><td>82  </td><td>9   </td><td>20  </td></tr>\n\t<tr><th scope=row>144</th><td>13  </td><td>238 </td><td>12.6</td><td>64  </td><td>9   </td><td>21  </td></tr>\n\t<tr><th scope=row>145</th><td>23  </td><td> 14 </td><td> 9.2</td><td>71  </td><td>9   </td><td>22  </td></tr>\n\t<tr><th scope=row>146</th><td>36  </td><td>139 </td><td>10.3</td><td>81  </td><td>9   </td><td>23  </td></tr>\n\t<tr><th scope=row>147</th><td> 7  </td><td> 49 </td><td>10.3</td><td>69  </td><td>9   </td><td>24  </td></tr>\n\t<tr><th scope=row>148</th><td>14  </td><td> 20 </td><td>16.6</td><td>63  </td><td>9   </td><td>25  </td></tr>\n\t<tr><th scope=row>149</th><td>30  </td><td>193 </td><td> 6.9</td><td>70  </td><td>9   </td><td>26  </td></tr>\n\t<tr><th scope=row>151</th><td>14  </td><td>191 </td><td>14.3</td><td>75  </td><td>9   </td><td>28  </td></tr>\n\t<tr><th scope=row>152</th><td>18  </td><td>131 </td><td> 8.0</td><td>76  </td><td>9   </td><td>29  </td></tr>\n\t<tr><th scope=row>153</th><td>20  </td><td>223 </td><td>11.5</td><td>68  </td><td>9   </td><td>30  </td></tr>\n</tbody>\n</table>\n",
   "text/latex": "\\begin{tabular}{r|llllll}\n  & Ozone & Solar.R & Wind & Temp & Month & Day\\\\\n\\hline\n\t1 & 41   & 190  &  7.4 & 67   & 5    &  1  \\\\\n\t2 & 36   & 118  &  8.0 & 72   & 5    &  2  \\\\\n\t3 & 12   & 149  & 12.6 & 74   & 5    &  3  \\\\\n\t4 & 18   & 313  & 11.5 & 62   & 5    &  4  \\\\\n\t7 & 23   & 299  &  8.6 & 65   & 5    &  7  \\\\\n\t8 & 19   &  99  & 13.8 & 59   & 5    &  8  \\\\\n\t9 &  8   &  19  & 20.1 & 61   & 5    &  9  \\\\\n\t12 & 16   & 256  &  9.7 & 69   & 5    & 12  \\\\\n\t13 & 11   & 290  &  9.2 & 66   & 5    & 13  \\\\\n\t14 & 14   & 274  & 10.9 & 68   & 5    & 14  \\\\\n\t15 & 18   &  65  & 13.2 & 58   & 5    & 15  \\\\\n\t16 & 14   & 334  & 11.5 & 64   & 5    & 16  \\\\\n\t17 & 34   & 307  & 12.0 & 66   & 5    & 17  \\\\\n\t18 &  6   &  78  & 18.4 & 57   & 5    & 18  \\\\\n\t19 & 30   & 322  & 11.5 & 68   & 5    & 19  \\\\\n\t20 & 11   &  44  &  9.7 & 62   & 5    & 20  \\\\\n\t21 &  1   &   8  &  9.7 & 59   & 5    & 21  \\\\\n\t22 & 11   & 320  & 16.6 & 73   & 5    & 22  \\\\\n\t23 &  4   &  25  &  9.7 & 61   & 5    & 23  \\\\\n\t24 & 32   &  92  & 12.0 & 61   & 5    & 24  \\\\\n\t28 & 23   &  13  & 12.0 & 67   & 5    & 28  \\\\\n\t29 & 45   & 252  & 14.9 & 81   & 5    & 29  \\\\\n\t31 & 37   & 279  &  7.4 & 76   & 5    & 31  \\\\\n\t38 & 29   & 127  &  9.7 & 82   & 6    &  7  \\\\\n\t41 & 39   & 323  & 11.5 & 87   & 6    & 10  \\\\\n\t44 & 23   & 148  &  8.0 & 82   & 6    & 13  \\\\\n\t47 & 21   & 191  & 14.9 & 77   & 6    & 16  \\\\\n\t48 & 37   & 284  & 20.7 & 72   & 6    & 17  \\\\\n\t49 & 20   &  37  &  9.2 & 65   & 6    & 18  \\\\\n\t50 & 12   & 120  & 11.5 & 73   & 6    & 19  \\\\\n\t... & ... & ... & ... & ... & ... & ...\\\\\n\t111 & 31   & 244  & 10.9 & 78   & 8    & 19  \\\\\n\t112 & 44   & 190  & 10.3 & 78   & 8    & 20  \\\\\n\t113 & 21   & 259  & 15.5 & 77   & 8    & 21  \\\\\n\t114 &  9   &  36  & 14.3 & 72   & 8    & 22  \\\\\n\t116 & 45   & 212  &  9.7 & 79   & 8    & 24  \\\\\n\t128 & 47   &  95  &  7.4 & 87   & 9    &  5  \\\\\n\t129 & 32   &  92  & 15.5 & 84   & 9    &  6  \\\\\n\t130 & 20   & 252  & 10.9 & 80   & 9    &  7  \\\\\n\t131 & 23   & 220  & 10.3 & 78   & 9    &  8  \\\\\n\t132 & 21   & 230  & 10.9 & 75   & 9    &  9  \\\\\n\t133 & 24   & 259  &  9.7 & 73   & 9    & 10  \\\\\n\t134 & 44   & 236  & 14.9 & 81   & 9    & 11  \\\\\n\t135 & 21   & 259  & 15.5 & 76   & 9    & 12  \\\\\n\t136 & 28   & 238  &  6.3 & 77   & 9    & 13  \\\\\n\t137 &  9   &  24  & 10.9 & 71   & 9    & 14  \\\\\n\t138 & 13   & 112  & 11.5 & 71   & 9    & 15  \\\\\n\t139 & 46   & 237  &  6.9 & 78   & 9    & 16  \\\\\n\t140 & 18   & 224  & 13.8 & 67   & 9    & 17  \\\\\n\t141 & 13   &  27  & 10.3 & 76   & 9    & 18  \\\\\n\t142 & 24   & 238  & 10.3 & 68   & 9    & 19  \\\\\n\t143 & 16   & 201  &  8.0 & 82   & 9    & 20  \\\\\n\t144 & 13   & 238  & 12.6 & 64   & 9    & 21  \\\\\n\t145 & 23   &  14  &  9.2 & 71   & 9    & 22  \\\\\n\t146 & 36   & 139  & 10.3 & 81   & 9    & 23  \\\\\n\t147 &  7   &  49  & 10.3 & 69   & 9    & 24  \\\\\n\t148 & 14   &  20  & 16.6 & 63   & 9    & 25  \\\\\n\t149 & 30   & 193  &  6.9 & 70   & 9    & 26  \\\\\n\t151 & 14   & 191  & 14.3 & 75   & 9    & 28  \\\\\n\t152 & 18   & 131  &  8.0 & 76   & 9    & 29  \\\\\n\t153 & 20   & 223  & 11.5 & 68   & 9    & 30  \\\\\n\\end{tabular}\n",
   "text/markdown": "\n| <!--/--> | Ozone | Solar.R | Wind | Temp | Month | Day | \n|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|\n| 1 | 41   | 190  |  7.4 | 67   | 5    |  1   | \n| 2 | 36   | 118  |  8.0 | 72   | 5    |  2   | \n| 3 | 12   | 149  | 12.6 | 74   | 5    |  3   | \n| 4 | 18   | 313  | 11.5 | 62   | 5    |  4   | \n| 7 | 23   | 299  |  8.6 | 65   | 5    |  7   | \n| 8 | 19   |  99  | 13.8 | 59   | 5    |  8   | \n| 9 |  8   |  19  | 20.1 | 61   | 5    |  9   | \n| 12 | 16   | 256  |  9.7 | 69   | 5    | 12   | \n| 13 | 11   | 290  |  9.2 | 66   | 5    | 13   | \n| 14 | 14   | 274  | 10.9 | 68   | 5    | 14   | \n| 15 | 18   |  65  | 13.2 | 58   | 5    | 15   | \n| 16 | 14   | 334  | 11.5 | 64   | 5    | 16   | \n| 17 | 34   | 307  | 12.0 | 66   | 5    | 17   | \n| 18 |  6   |  78  | 18.4 | 57   | 5    | 18   | \n| 19 | 30   | 322  | 11.5 | 68   | 5    | 19   | \n| 20 | 11   |  44  |  9.7 | 62   | 5    | 20   | \n| 21 |  1   |   8  |  9.7 | 59   | 5    | 21   | \n| 22 | 11   | 320  | 16.6 | 73   | 5    | 22   | \n| 23 |  4   |  25  |  9.7 | 61   | 5    | 23   | \n| 24 | 32   |  92  | 12.0 | 61   | 5    | 24   | \n| 28 | 23   |  13  | 12.0 | 67   | 5    | 28   | \n| 29 | 45   | 252  | 14.9 | 81   | 5    | 29   | \n| 31 | 37   | 279  |  7.4 | 76   | 5    | 31   | \n| 38 | 29   | 127  |  9.7 | 82   | 6    |  7   | \n| 41 | 39   | 323  | 11.5 | 87   | 6    | 10   | \n| 44 | 23   | 148  |  8.0 | 82   | 6    | 13   | \n| 47 | 21   | 191  | 14.9 | 77   | 6    | 16   | \n| 48 | 37   | 284  | 20.7 | 72   | 6    | 17   | \n| 49 | 20   |  37  |  9.2 | 65   | 6    | 18   | \n| 50 | 12   | 120  | 11.5 | 73   | 6    | 19   | \n| ... | ... | ... | ... | ... | ... | ... | \n| 111 | 31   | 244  | 10.9 | 78   | 8    | 19   | \n| 112 | 44   | 190  | 10.3 | 78   | 8    | 20   | \n| 113 | 21   | 259  | 15.5 | 77   | 8    | 21   | \n| 114 |  9   |  36  | 14.3 | 72   | 8    | 22   | \n| 116 | 45   | 212  |  9.7 | 79   | 8    | 24   | \n| 128 | 47   |  95  |  7.4 | 87   | 9    |  5   | \n| 129 | 32   |  92  | 15.5 | 84   | 9    |  6   | \n| 130 | 20   | 252  | 10.9 | 80   | 9    |  7   | \n| 131 | 23   | 220  | 10.3 | 78   | 9    |  8   | \n| 132 | 21   | 230  | 10.9 | 75   | 9    |  9   | \n| 133 | 24   | 259  |  9.7 | 73   | 9    | 10   | \n| 134 | 44   | 236  | 14.9 | 81   | 9    | 11   | \n| 135 | 21   | 259  | 15.5 | 76   | 9    | 12   | \n| 136 | 28   | 238  |  6.3 | 77   | 9    | 13   | \n| 137 |  9   |  24  | 10.9 | 71   | 9    | 14   | \n| 138 | 13   | 112  | 11.5 | 71   | 9    | 15   | \n| 139 | 46   | 237  |  6.9 | 78   | 9    | 16   | \n| 140 | 18   | 224  | 13.8 | 67   | 9    | 17   | \n| 141 | 13   |  27  | 10.3 | 76   | 9    | 18   | \n| 142 | 24   | 238  | 10.3 | 68   | 9    | 19   | \n| 143 | 16   | 201  |  8.0 | 82   | 9    | 20   | \n| 144 | 13   | 238  | 12.6 | 64   | 9    | 21   | \n| 145 | 23   |  14  |  9.2 | 71   | 9    | 22   | \n| 146 | 36   | 139  | 10.3 | 81   | 9    | 23   | \n| 147 |  7   |  49  | 10.3 | 69   | 9    | 24   | \n| 148 | 14   |  20  | 16.6 | 63   | 9    | 25   | \n| 149 | 30   | 193  |  6.9 | 70   | 9    | 26   | \n| 151 | 14   | 191  | 14.3 | 75   | 9    | 28   | \n| 152 | 18   | 131  |  8.0 | 76   | 9    | 29   | \n| 153 | 20   | 223  | 11.5 | 68   | 9    | 30   | \n\n\n",
   "text/plain": "    Ozone Solar.R Wind Temp Month Day\n1   41    190      7.4 67   5      1 \n2   36    118      8.0 72   5      2 \n3   12    149     12.6 74   5      3 \n4   18    313     11.5 62   5      4 \n7   23    299      8.6 65   5      7 \n8   19     99     13.8 59   5      8 \n9    8     19     20.1 61   5      9 \n12  16    256      9.7 69   5     12 \n13  11    290      9.2 66   5     13 \n14  14    274     10.9 68   5     14 \n15  18     65     13.2 58   5     15 \n16  14    334     11.5 64   5     16 \n17  34    307     12.0 66   5     17 \n18   6     78     18.4 57   5     18 \n19  30    322     11.5 68   5     19 \n20  11     44      9.7 62   5     20 \n21   1      8      9.7 59   5     21 \n22  11    320     16.6 73   5     22 \n23   4     25      9.7 61   5     23 \n24  32     92     12.0 61   5     24 \n28  23     13     12.0 67   5     28 \n29  45    252     14.9 81   5     29 \n31  37    279      7.4 76   5     31 \n38  29    127      9.7 82   6      7 \n41  39    323     11.5 87   6     10 \n44  23    148      8.0 82   6     13 \n47  21    191     14.9 77   6     16 \n48  37    284     20.7 72   6     17 \n49  20     37      9.2 65   6     18 \n50  12    120     11.5 73   6     19 \n... ...   ...     ...  ...  ...   ...\n111 31    244     10.9 78   8     19 \n112 44    190     10.3 78   8     20 \n113 21    259     15.5 77   8     21 \n114  9     36     14.3 72   8     22 \n116 45    212      9.7 79   8     24 \n128 47     95      7.4 87   9      5 \n129 32     92     15.5 84   9      6 \n130 20    252     10.9 80   9      7 \n131 23    220     10.3 78   9      8 \n132 21    230     10.9 75   9      9 \n133 24    259      9.7 73   9     10 \n134 44    236     14.9 81   9     11 \n135 21    259     15.5 76   9     12 \n136 28    238      6.3 77   9     13 \n137  9     24     10.9 71   9     14 \n138 13    112     11.5 71   9     15 \n139 46    237      6.9 78   9     16 \n140 18    224     13.8 67   9     17 \n141 13     27     10.3 76   9     18 \n142 24    238     10.3 68   9     19 \n143 16    201      8.0 82   9     20 \n144 13    238     12.6 64   9     21 \n145 23     14      9.2 71   9     22 \n146 36    139     10.3 81   9     23 \n147  7     49     10.3 69   9     24 \n148 14     20     16.6 63   9     25 \n149 30    193      6.9 70   9     26 \n151 14    191     14.3 75   9     28 \n152 18    131      8.0 76   9     29 \n153 20    223     11.5 68   9     30 "
  },
  "metadata": {},
  "output_type": "display_data"
 }
]
```

Suppose we want to define a day with good quality air as one with ozone levels
below 60ppb, and temperatures less than 80 degrees F. Write an R loop to do
this, and output the resulting subset of the data to a file called
goodquality.txt. (Hint: use an ifelse() statement inside the for loop.)

```{.python .input  n=31}
airquality$Temp
```

```{.json .output n=31}
[
 {
  "data": {
   "text/html": "<ol class=list-inline>\n\t<li>67</li>\n\t<li>72</li>\n\t<li>74</li>\n\t<li>62</li>\n\t<li>56</li>\n\t<li>66</li>\n\t<li>65</li>\n\t<li>59</li>\n\t<li>61</li>\n\t<li>69</li>\n\t<li>74</li>\n\t<li>69</li>\n\t<li>66</li>\n\t<li>68</li>\n\t<li>58</li>\n\t<li>64</li>\n\t<li>66</li>\n\t<li>57</li>\n\t<li>68</li>\n\t<li>62</li>\n\t<li>59</li>\n\t<li>73</li>\n\t<li>61</li>\n\t<li>61</li>\n\t<li>57</li>\n\t<li>58</li>\n\t<li>57</li>\n\t<li>67</li>\n\t<li>81</li>\n\t<li>79</li>\n\t<li>76</li>\n\t<li>78</li>\n\t<li>74</li>\n\t<li>67</li>\n\t<li>84</li>\n\t<li>85</li>\n\t<li>79</li>\n\t<li>82</li>\n\t<li>87</li>\n\t<li>90</li>\n\t<li>87</li>\n\t<li>93</li>\n\t<li>92</li>\n\t<li>82</li>\n\t<li>80</li>\n\t<li>79</li>\n\t<li>77</li>\n\t<li>72</li>\n\t<li>65</li>\n\t<li>73</li>\n\t<li>76</li>\n\t<li>77</li>\n\t<li>76</li>\n\t<li>76</li>\n\t<li>76</li>\n\t<li>75</li>\n\t<li>78</li>\n\t<li>73</li>\n\t<li>80</li>\n\t<li>77</li>\n\t<li>83</li>\n\t<li>84</li>\n\t<li>85</li>\n\t<li>81</li>\n\t<li>84</li>\n\t<li>83</li>\n\t<li>83</li>\n\t<li>88</li>\n\t<li>92</li>\n\t<li>92</li>\n\t<li>89</li>\n\t<li>82</li>\n\t<li>73</li>\n\t<li>81</li>\n\t<li>91</li>\n\t<li>80</li>\n\t<li>81</li>\n\t<li>82</li>\n\t<li>84</li>\n\t<li>87</li>\n\t<li>85</li>\n\t<li>74</li>\n\t<li>81</li>\n\t<li>82</li>\n\t<li>86</li>\n\t<li>85</li>\n\t<li>82</li>\n\t<li>86</li>\n\t<li>88</li>\n\t<li>86</li>\n\t<li>83</li>\n\t<li>81</li>\n\t<li>81</li>\n\t<li>81</li>\n\t<li>82</li>\n\t<li>86</li>\n\t<li>85</li>\n\t<li>87</li>\n\t<li>89</li>\n\t<li>90</li>\n\t<li>90</li>\n\t<li>92</li>\n\t<li>86</li>\n\t<li>86</li>\n\t<li>82</li>\n\t<li>80</li>\n\t<li>79</li>\n\t<li>77</li>\n\t<li>79</li>\n\t<li>76</li>\n\t<li>78</li>\n\t<li>78</li>\n\t<li>77</li>\n\t<li>72</li>\n\t<li>75</li>\n\t<li>79</li>\n\t<li>81</li>\n\t<li>86</li>\n\t<li>88</li>\n\t<li>97</li>\n\t<li>94</li>\n\t<li>96</li>\n\t<li>94</li>\n\t<li>91</li>\n\t<li>92</li>\n\t<li>93</li>\n\t<li>93</li>\n\t<li>87</li>\n\t<li>84</li>\n\t<li>80</li>\n\t<li>78</li>\n\t<li>75</li>\n\t<li>73</li>\n\t<li>81</li>\n\t<li>76</li>\n\t<li>77</li>\n\t<li>71</li>\n\t<li>71</li>\n\t<li>78</li>\n\t<li>67</li>\n\t<li>76</li>\n\t<li>68</li>\n\t<li>82</li>\n\t<li>64</li>\n\t<li>71</li>\n\t<li>81</li>\n\t<li>69</li>\n\t<li>63</li>\n\t<li>70</li>\n\t<li>77</li>\n\t<li>75</li>\n\t<li>76</li>\n\t<li>68</li>\n</ol>\n",
   "text/latex": "\\begin{enumerate*}\n\\item 67\n\\item 72\n\\item 74\n\\item 62\n\\item 56\n\\item 66\n\\item 65\n\\item 59\n\\item 61\n\\item 69\n\\item 74\n\\item 69\n\\item 66\n\\item 68\n\\item 58\n\\item 64\n\\item 66\n\\item 57\n\\item 68\n\\item 62\n\\item 59\n\\item 73\n\\item 61\n\\item 61\n\\item 57\n\\item 58\n\\item 57\n\\item 67\n\\item 81\n\\item 79\n\\item 76\n\\item 78\n\\item 74\n\\item 67\n\\item 84\n\\item 85\n\\item 79\n\\item 82\n\\item 87\n\\item 90\n\\item 87\n\\item 93\n\\item 92\n\\item 82\n\\item 80\n\\item 79\n\\item 77\n\\item 72\n\\item 65\n\\item 73\n\\item 76\n\\item 77\n\\item 76\n\\item 76\n\\item 76\n\\item 75\n\\item 78\n\\item 73\n\\item 80\n\\item 77\n\\item 83\n\\item 84\n\\item 85\n\\item 81\n\\item 84\n\\item 83\n\\item 83\n\\item 88\n\\item 92\n\\item 92\n\\item 89\n\\item 82\n\\item 73\n\\item 81\n\\item 91\n\\item 80\n\\item 81\n\\item 82\n\\item 84\n\\item 87\n\\item 85\n\\item 74\n\\item 81\n\\item 82\n\\item 86\n\\item 85\n\\item 82\n\\item 86\n\\item 88\n\\item 86\n\\item 83\n\\item 81\n\\item 81\n\\item 81\n\\item 82\n\\item 86\n\\item 85\n\\item 87\n\\item 89\n\\item 90\n\\item 90\n\\item 92\n\\item 86\n\\item 86\n\\item 82\n\\item 80\n\\item 79\n\\item 77\n\\item 79\n\\item 76\n\\item 78\n\\item 78\n\\item 77\n\\item 72\n\\item 75\n\\item 79\n\\item 81\n\\item 86\n\\item 88\n\\item 97\n\\item 94\n\\item 96\n\\item 94\n\\item 91\n\\item 92\n\\item 93\n\\item 93\n\\item 87\n\\item 84\n\\item 80\n\\item 78\n\\item 75\n\\item 73\n\\item 81\n\\item 76\n\\item 77\n\\item 71\n\\item 71\n\\item 78\n\\item 67\n\\item 76\n\\item 68\n\\item 82\n\\item 64\n\\item 71\n\\item 81\n\\item 69\n\\item 63\n\\item 70\n\\item 77\n\\item 75\n\\item 76\n\\item 68\n\\end{enumerate*}\n",
   "text/markdown": "1. 67\n2. 72\n3. 74\n4. 62\n5. 56\n6. 66\n7. 65\n8. 59\n9. 61\n10. 69\n11. 74\n12. 69\n13. 66\n14. 68\n15. 58\n16. 64\n17. 66\n18. 57\n19. 68\n20. 62\n21. 59\n22. 73\n23. 61\n24. 61\n25. 57\n26. 58\n27. 57\n28. 67\n29. 81\n30. 79\n31. 76\n32. 78\n33. 74\n34. 67\n35. 84\n36. 85\n37. 79\n38. 82\n39. 87\n40. 90\n41. 87\n42. 93\n43. 92\n44. 82\n45. 80\n46. 79\n47. 77\n48. 72\n49. 65\n50. 73\n51. 76\n52. 77\n53. 76\n54. 76\n55. 76\n56. 75\n57. 78\n58. 73\n59. 80\n60. 77\n61. 83\n62. 84\n63. 85\n64. 81\n65. 84\n66. 83\n67. 83\n68. 88\n69. 92\n70. 92\n71. 89\n72. 82\n73. 73\n74. 81\n75. 91\n76. 80\n77. 81\n78. 82\n79. 84\n80. 87\n81. 85\n82. 74\n83. 81\n84. 82\n85. 86\n86. 85\n87. 82\n88. 86\n89. 88\n90. 86\n91. 83\n92. 81\n93. 81\n94. 81\n95. 82\n96. 86\n97. 85\n98. 87\n99. 89\n100. 90\n101. 90\n102. 92\n103. 86\n104. 86\n105. 82\n106. 80\n107. 79\n108. 77\n109. 79\n110. 76\n111. 78\n112. 78\n113. 77\n114. 72\n115. 75\n116. 79\n117. 81\n118. 86\n119. 88\n120. 97\n121. 94\n122. 96\n123. 94\n124. 91\n125. 92\n126. 93\n127. 93\n128. 87\n129. 84\n130. 80\n131. 78\n132. 75\n133. 73\n134. 81\n135. 76\n136. 77\n137. 71\n138. 71\n139. 78\n140. 67\n141. 76\n142. 68\n143. 82\n144. 64\n145. 71\n146. 81\n147. 69\n148. 63\n149. 70\n150. 77\n151. 75\n152. 76\n153. 68\n\n\n",
   "text/plain": "  [1] 67 72 74 62 56 66 65 59 61 69 74 69 66 68 58 64 66 57 68 62 59 73 61 61 57\n [26] 58 57 67 81 79 76 78 74 67 84 85 79 82 87 90 87 93 92 82 80 79 77 72 65 73\n [51] 76 77 76 76 76 75 78 73 80 77 83 84 85 81 84 83 83 88 92 92 89 82 73 81 91\n [76] 80 81 82 84 87 85 74 81 82 86 85 82 86 88 86 83 81 81 81 82 86 85 87 89 90\n[101] 90 92 86 86 82 80 79 77 79 76 78 78 77 72 75 79 81 86 88 97 94 96 94 91 92\n[126] 93 93 87 84 80 78 75 73 81 76 77 71 71 78 67 76 68 82 64 71 81 69 63 70 77\n[151] 75 76 68"
  },
  "metadata": {},
  "output_type": "display_data"
 }
]
```

```R
for(i in 1:numdays1)
ifelse(airquality$Ozone[i] <60 &
airquality$Temp<80,goodair1[i] = 1,goodair1[i] = 0)
#here it's not working
because of "=" sign , let's change to different assignment operator <-
```

```{.python .input  n=32}
for(i in 1:numdays)
  ifelse(airquality$Ozone[i] <60 && airquality$Temp<80,goodair[i] <- 1,goodair[i] <- 0)

```

```{.python .input  n=33}
goodindices1 <-  which(goodair == 1)
#airquality[goodindices1,] 
print(goodindices1)
```

```{.json .output n=33}
[
 {
  "name": "stdout",
  "output_type": "stream",
  "text": " [1]   1   2   3   4   5   6   7   8   9  10  11  12  13  14  15  16  17  18  19\n[20]  20  21  22  23  24  25  27  28  29  31  32  33  35  36  38  41  43  44  45\n[39]  46  47  48  49  50  51  54  55  57  59  60  61  63  64  67  72  73  74  75\n[58]  76  77  78  82  87  88  90  92  93  94  95  97 102 103 104 105 107 108 109\n[77] 110 111\n"
 }
]
```

```{.python .input  n=34}
airquality[goodindices1,]
```

```{.json .output n=34}
[
 {
  "data": {
   "text/html": "<table>\n<thead><tr><th></th><th scope=col>Ozone</th><th scope=col>Solar.R</th><th scope=col>Wind</th><th scope=col>Temp</th><th scope=col>Month</th><th scope=col>Day</th></tr></thead>\n<tbody>\n\t<tr><th scope=row>1</th><td>41  </td><td>190 </td><td> 7.4</td><td>67  </td><td>5   </td><td> 1  </td></tr>\n\t<tr><th scope=row>2</th><td>36  </td><td>118 </td><td> 8.0</td><td>72  </td><td>5   </td><td> 2  </td></tr>\n\t<tr><th scope=row>3</th><td>12  </td><td>149 </td><td>12.6</td><td>74  </td><td>5   </td><td> 3  </td></tr>\n\t<tr><th scope=row>4</th><td>18  </td><td>313 </td><td>11.5</td><td>62  </td><td>5   </td><td> 4  </td></tr>\n\t<tr><th scope=row>5</th><td>NA  </td><td> NA </td><td>14.3</td><td>56  </td><td>5   </td><td> 5  </td></tr>\n\t<tr><th scope=row>6</th><td>28  </td><td> NA </td><td>14.9</td><td>66  </td><td>5   </td><td> 6  </td></tr>\n\t<tr><th scope=row>7</th><td>23  </td><td>299 </td><td> 8.6</td><td>65  </td><td>5   </td><td> 7  </td></tr>\n\t<tr><th scope=row>8</th><td>19  </td><td> 99 </td><td>13.8</td><td>59  </td><td>5   </td><td> 8  </td></tr>\n\t<tr><th scope=row>9</th><td> 8  </td><td> 19 </td><td>20.1</td><td>61  </td><td>5   </td><td> 9  </td></tr>\n\t<tr><th scope=row>10</th><td>NA  </td><td>194 </td><td> 8.6</td><td>69  </td><td>5   </td><td>10  </td></tr>\n\t<tr><th scope=row>11</th><td> 7  </td><td> NA </td><td> 6.9</td><td>74  </td><td>5   </td><td>11  </td></tr>\n\t<tr><th scope=row>12</th><td>16  </td><td>256 </td><td> 9.7</td><td>69  </td><td>5   </td><td>12  </td></tr>\n\t<tr><th scope=row>13</th><td>11  </td><td>290 </td><td> 9.2</td><td>66  </td><td>5   </td><td>13  </td></tr>\n\t<tr><th scope=row>14</th><td>14  </td><td>274 </td><td>10.9</td><td>68  </td><td>5   </td><td>14  </td></tr>\n\t<tr><th scope=row>15</th><td>18  </td><td> 65 </td><td>13.2</td><td>58  </td><td>5   </td><td>15  </td></tr>\n\t<tr><th scope=row>16</th><td>14  </td><td>334 </td><td>11.5</td><td>64  </td><td>5   </td><td>16  </td></tr>\n\t<tr><th scope=row>17</th><td>34  </td><td>307 </td><td>12.0</td><td>66  </td><td>5   </td><td>17  </td></tr>\n\t<tr><th scope=row>18</th><td> 6  </td><td> 78 </td><td>18.4</td><td>57  </td><td>5   </td><td>18  </td></tr>\n\t<tr><th scope=row>19</th><td>30  </td><td>322 </td><td>11.5</td><td>68  </td><td>5   </td><td>19  </td></tr>\n\t<tr><th scope=row>20</th><td>11  </td><td> 44 </td><td> 9.7</td><td>62  </td><td>5   </td><td>20  </td></tr>\n\t<tr><th scope=row>21</th><td> 1  </td><td>  8 </td><td> 9.7</td><td>59  </td><td>5   </td><td>21  </td></tr>\n\t<tr><th scope=row>22</th><td>11  </td><td>320 </td><td>16.6</td><td>73  </td><td>5   </td><td>22  </td></tr>\n\t<tr><th scope=row>23</th><td> 4  </td><td> 25 </td><td> 9.7</td><td>61  </td><td>5   </td><td>23  </td></tr>\n\t<tr><th scope=row>24</th><td>32  </td><td> 92 </td><td>12.0</td><td>61  </td><td>5   </td><td>24  </td></tr>\n\t<tr><th scope=row>25</th><td>NA  </td><td> 66 </td><td>16.6</td><td>57  </td><td>5   </td><td>25  </td></tr>\n\t<tr><th scope=row>27</th><td>NA  </td><td> NA </td><td> 8.0</td><td>57  </td><td>5   </td><td>27  </td></tr>\n\t<tr><th scope=row>28</th><td>23  </td><td> 13 </td><td>12.0</td><td>67  </td><td>5   </td><td>28  </td></tr>\n\t<tr><th scope=row>29</th><td>45  </td><td>252 </td><td>14.9</td><td>81  </td><td>5   </td><td>29  </td></tr>\n\t<tr><th scope=row>31</th><td>37  </td><td>279 </td><td> 7.4</td><td>76  </td><td>5   </td><td>31  </td></tr>\n\t<tr><th scope=row>32</th><td>NA  </td><td>286 </td><td> 8.6</td><td>78  </td><td>6   </td><td> 1  </td></tr>\n\t<tr><th scope=row>...</th><td>...</td><td>...</td><td>...</td><td>...</td><td>...</td><td>...</td></tr>\n\t<tr><th scope=row>60</th><td>NA  </td><td> 31 </td><td>14.9</td><td>77  </td><td>6   </td><td>29  </td></tr>\n\t<tr><th scope=row>61</th><td>NA  </td><td>138 </td><td> 8.0</td><td>83  </td><td>6   </td><td>30  </td></tr>\n\t<tr><th scope=row>63</th><td>49  </td><td>248 </td><td> 9.2</td><td>85  </td><td>7   </td><td> 2  </td></tr>\n\t<tr><th scope=row>64</th><td>32  </td><td>236 </td><td> 9.2</td><td>81  </td><td>7   </td><td> 3  </td></tr>\n\t<tr><th scope=row>67</th><td>40  </td><td>314 </td><td>10.9</td><td>83  </td><td>7   </td><td> 6  </td></tr>\n\t<tr><th scope=row>72</th><td>NA  </td><td>139 </td><td> 8.6</td><td>82  </td><td>7   </td><td>11  </td></tr>\n\t<tr><th scope=row>73</th><td>10  </td><td>264 </td><td>14.3</td><td>73  </td><td>7   </td><td>12  </td></tr>\n\t<tr><th scope=row>74</th><td>27  </td><td>175 </td><td>14.9</td><td>81  </td><td>7   </td><td>13  </td></tr>\n\t<tr><th scope=row>75</th><td>NA  </td><td>291 </td><td>14.9</td><td>91  </td><td>7   </td><td>14  </td></tr>\n\t<tr><th scope=row>76</th><td> 7  </td><td> 48 </td><td>14.3</td><td>80  </td><td>7   </td><td>15  </td></tr>\n\t<tr><th scope=row>77</th><td>48  </td><td>260 </td><td> 6.9</td><td>81  </td><td>7   </td><td>16  </td></tr>\n\t<tr><th scope=row>78</th><td>35  </td><td>274 </td><td>10.3</td><td>82  </td><td>7   </td><td>17  </td></tr>\n\t<tr><th scope=row>82</th><td>16  </td><td>  7 </td><td> 6.9</td><td>74  </td><td>7   </td><td>21  </td></tr>\n\t<tr><th scope=row>87</th><td>20  </td><td> 81 </td><td> 8.6</td><td>82  </td><td>7   </td><td>26  </td></tr>\n\t<tr><th scope=row>88</th><td>52  </td><td> 82 </td><td>12.0</td><td>86  </td><td>7   </td><td>27  </td></tr>\n\t<tr><th scope=row>90</th><td>50  </td><td>275 </td><td> 7.4</td><td>86  </td><td>7   </td><td>29  </td></tr>\n\t<tr><th scope=row>92</th><td>59  </td><td>254 </td><td> 9.2</td><td>81  </td><td>7   </td><td>31  </td></tr>\n\t<tr><th scope=row>93</th><td>39  </td><td> 83 </td><td> 6.9</td><td>81  </td><td>8   </td><td> 1  </td></tr>\n\t<tr><th scope=row>94</th><td> 9  </td><td> 24 </td><td>13.8</td><td>81  </td><td>8   </td><td> 2  </td></tr>\n\t<tr><th scope=row>95</th><td>16  </td><td> 77 </td><td> 7.4</td><td>82  </td><td>8   </td><td> 3  </td></tr>\n\t<tr><th scope=row>97</th><td>35  </td><td> NA </td><td> 7.4</td><td>85  </td><td>8   </td><td> 5  </td></tr>\n\t<tr><th scope=row>102</th><td>NA  </td><td>222 </td><td> 8.6</td><td>92  </td><td>8   </td><td>10  </td></tr>\n\t<tr><th scope=row>103</th><td>NA  </td><td>137 </td><td>11.5</td><td>86  </td><td>8   </td><td>11  </td></tr>\n\t<tr><th scope=row>104</th><td>44  </td><td>192 </td><td>11.5</td><td>86  </td><td>8   </td><td>12  </td></tr>\n\t<tr><th scope=row>105</th><td>28  </td><td>273 </td><td>11.5</td><td>82  </td><td>8   </td><td>13  </td></tr>\n\t<tr><th scope=row>107</th><td>NA  </td><td> 64 </td><td>11.5</td><td>79  </td><td>8   </td><td>15  </td></tr>\n\t<tr><th scope=row>108</th><td>22  </td><td> 71 </td><td>10.3</td><td>77  </td><td>8   </td><td>16  </td></tr>\n\t<tr><th scope=row>109</th><td>59  </td><td> 51 </td><td> 6.3</td><td>79  </td><td>8   </td><td>17  </td></tr>\n\t<tr><th scope=row>110</th><td>23  </td><td>115 </td><td> 7.4</td><td>76  </td><td>8   </td><td>18  </td></tr>\n\t<tr><th scope=row>111</th><td>31  </td><td>244 </td><td>10.9</td><td>78  </td><td>8   </td><td>19  </td></tr>\n</tbody>\n</table>\n",
   "text/latex": "\\begin{tabular}{r|llllll}\n  & Ozone & Solar.R & Wind & Temp & Month & Day\\\\\n\\hline\n\t1 & 41   & 190  &  7.4 & 67   & 5    &  1  \\\\\n\t2 & 36   & 118  &  8.0 & 72   & 5    &  2  \\\\\n\t3 & 12   & 149  & 12.6 & 74   & 5    &  3  \\\\\n\t4 & 18   & 313  & 11.5 & 62   & 5    &  4  \\\\\n\t5 & NA   &  NA  & 14.3 & 56   & 5    &  5  \\\\\n\t6 & 28   &  NA  & 14.9 & 66   & 5    &  6  \\\\\n\t7 & 23   & 299  &  8.6 & 65   & 5    &  7  \\\\\n\t8 & 19   &  99  & 13.8 & 59   & 5    &  8  \\\\\n\t9 &  8   &  19  & 20.1 & 61   & 5    &  9  \\\\\n\t10 & NA   & 194  &  8.6 & 69   & 5    & 10  \\\\\n\t11 &  7   &  NA  &  6.9 & 74   & 5    & 11  \\\\\n\t12 & 16   & 256  &  9.7 & 69   & 5    & 12  \\\\\n\t13 & 11   & 290  &  9.2 & 66   & 5    & 13  \\\\\n\t14 & 14   & 274  & 10.9 & 68   & 5    & 14  \\\\\n\t15 & 18   &  65  & 13.2 & 58   & 5    & 15  \\\\\n\t16 & 14   & 334  & 11.5 & 64   & 5    & 16  \\\\\n\t17 & 34   & 307  & 12.0 & 66   & 5    & 17  \\\\\n\t18 &  6   &  78  & 18.4 & 57   & 5    & 18  \\\\\n\t19 & 30   & 322  & 11.5 & 68   & 5    & 19  \\\\\n\t20 & 11   &  44  &  9.7 & 62   & 5    & 20  \\\\\n\t21 &  1   &   8  &  9.7 & 59   & 5    & 21  \\\\\n\t22 & 11   & 320  & 16.6 & 73   & 5    & 22  \\\\\n\t23 &  4   &  25  &  9.7 & 61   & 5    & 23  \\\\\n\t24 & 32   &  92  & 12.0 & 61   & 5    & 24  \\\\\n\t25 & NA   &  66  & 16.6 & 57   & 5    & 25  \\\\\n\t27 & NA   &  NA  &  8.0 & 57   & 5    & 27  \\\\\n\t28 & 23   &  13  & 12.0 & 67   & 5    & 28  \\\\\n\t29 & 45   & 252  & 14.9 & 81   & 5    & 29  \\\\\n\t31 & 37   & 279  &  7.4 & 76   & 5    & 31  \\\\\n\t32 & NA   & 286  &  8.6 & 78   & 6    &  1  \\\\\n\t... & ... & ... & ... & ... & ... & ...\\\\\n\t60 & NA   &  31  & 14.9 & 77   & 6    & 29  \\\\\n\t61 & NA   & 138  &  8.0 & 83   & 6    & 30  \\\\\n\t63 & 49   & 248  &  9.2 & 85   & 7    &  2  \\\\\n\t64 & 32   & 236  &  9.2 & 81   & 7    &  3  \\\\\n\t67 & 40   & 314  & 10.9 & 83   & 7    &  6  \\\\\n\t72 & NA   & 139  &  8.6 & 82   & 7    & 11  \\\\\n\t73 & 10   & 264  & 14.3 & 73   & 7    & 12  \\\\\n\t74 & 27   & 175  & 14.9 & 81   & 7    & 13  \\\\\n\t75 & NA   & 291  & 14.9 & 91   & 7    & 14  \\\\\n\t76 &  7   &  48  & 14.3 & 80   & 7    & 15  \\\\\n\t77 & 48   & 260  &  6.9 & 81   & 7    & 16  \\\\\n\t78 & 35   & 274  & 10.3 & 82   & 7    & 17  \\\\\n\t82 & 16   &   7  &  6.9 & 74   & 7    & 21  \\\\\n\t87 & 20   &  81  &  8.6 & 82   & 7    & 26  \\\\\n\t88 & 52   &  82  & 12.0 & 86   & 7    & 27  \\\\\n\t90 & 50   & 275  &  7.4 & 86   & 7    & 29  \\\\\n\t92 & 59   & 254  &  9.2 & 81   & 7    & 31  \\\\\n\t93 & 39   &  83  &  6.9 & 81   & 8    &  1  \\\\\n\t94 &  9   &  24  & 13.8 & 81   & 8    &  2  \\\\\n\t95 & 16   &  77  &  7.4 & 82   & 8    &  3  \\\\\n\t97 & 35   &  NA  &  7.4 & 85   & 8    &  5  \\\\\n\t102 & NA   & 222  &  8.6 & 92   & 8    & 10  \\\\\n\t103 & NA   & 137  & 11.5 & 86   & 8    & 11  \\\\\n\t104 & 44   & 192  & 11.5 & 86   & 8    & 12  \\\\\n\t105 & 28   & 273  & 11.5 & 82   & 8    & 13  \\\\\n\t107 & NA   &  64  & 11.5 & 79   & 8    & 15  \\\\\n\t108 & 22   &  71  & 10.3 & 77   & 8    & 16  \\\\\n\t109 & 59   &  51  &  6.3 & 79   & 8    & 17  \\\\\n\t110 & 23   & 115  &  7.4 & 76   & 8    & 18  \\\\\n\t111 & 31   & 244  & 10.9 & 78   & 8    & 19  \\\\\n\\end{tabular}\n",
   "text/markdown": "\n| <!--/--> | Ozone | Solar.R | Wind | Temp | Month | Day | \n|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|\n| 1 | 41   | 190  |  7.4 | 67   | 5    |  1   | \n| 2 | 36   | 118  |  8.0 | 72   | 5    |  2   | \n| 3 | 12   | 149  | 12.6 | 74   | 5    |  3   | \n| 4 | 18   | 313  | 11.5 | 62   | 5    |  4   | \n| 5 | NA   |  NA  | 14.3 | 56   | 5    |  5   | \n| 6 | 28   |  NA  | 14.9 | 66   | 5    |  6   | \n| 7 | 23   | 299  |  8.6 | 65   | 5    |  7   | \n| 8 | 19   |  99  | 13.8 | 59   | 5    |  8   | \n| 9 |  8   |  19  | 20.1 | 61   | 5    |  9   | \n| 10 | NA   | 194  |  8.6 | 69   | 5    | 10   | \n| 11 |  7   |  NA  |  6.9 | 74   | 5    | 11   | \n| 12 | 16   | 256  |  9.7 | 69   | 5    | 12   | \n| 13 | 11   | 290  |  9.2 | 66   | 5    | 13   | \n| 14 | 14   | 274  | 10.9 | 68   | 5    | 14   | \n| 15 | 18   |  65  | 13.2 | 58   | 5    | 15   | \n| 16 | 14   | 334  | 11.5 | 64   | 5    | 16   | \n| 17 | 34   | 307  | 12.0 | 66   | 5    | 17   | \n| 18 |  6   |  78  | 18.4 | 57   | 5    | 18   | \n| 19 | 30   | 322  | 11.5 | 68   | 5    | 19   | \n| 20 | 11   |  44  |  9.7 | 62   | 5    | 20   | \n| 21 |  1   |   8  |  9.7 | 59   | 5    | 21   | \n| 22 | 11   | 320  | 16.6 | 73   | 5    | 22   | \n| 23 |  4   |  25  |  9.7 | 61   | 5    | 23   | \n| 24 | 32   |  92  | 12.0 | 61   | 5    | 24   | \n| 25 | NA   |  66  | 16.6 | 57   | 5    | 25   | \n| 27 | NA   |  NA  |  8.0 | 57   | 5    | 27   | \n| 28 | 23   |  13  | 12.0 | 67   | 5    | 28   | \n| 29 | 45   | 252  | 14.9 | 81   | 5    | 29   | \n| 31 | 37   | 279  |  7.4 | 76   | 5    | 31   | \n| 32 | NA   | 286  |  8.6 | 78   | 6    |  1   | \n| ... | ... | ... | ... | ... | ... | ... | \n| 60 | NA   |  31  | 14.9 | 77   | 6    | 29   | \n| 61 | NA   | 138  |  8.0 | 83   | 6    | 30   | \n| 63 | 49   | 248  |  9.2 | 85   | 7    |  2   | \n| 64 | 32   | 236  |  9.2 | 81   | 7    |  3   | \n| 67 | 40   | 314  | 10.9 | 83   | 7    |  6   | \n| 72 | NA   | 139  |  8.6 | 82   | 7    | 11   | \n| 73 | 10   | 264  | 14.3 | 73   | 7    | 12   | \n| 74 | 27   | 175  | 14.9 | 81   | 7    | 13   | \n| 75 | NA   | 291  | 14.9 | 91   | 7    | 14   | \n| 76 |  7   |  48  | 14.3 | 80   | 7    | 15   | \n| 77 | 48   | 260  |  6.9 | 81   | 7    | 16   | \n| 78 | 35   | 274  | 10.3 | 82   | 7    | 17   | \n| 82 | 16   |   7  |  6.9 | 74   | 7    | 21   | \n| 87 | 20   |  81  |  8.6 | 82   | 7    | 26   | \n| 88 | 52   |  82  | 12.0 | 86   | 7    | 27   | \n| 90 | 50   | 275  |  7.4 | 86   | 7    | 29   | \n| 92 | 59   | 254  |  9.2 | 81   | 7    | 31   | \n| 93 | 39   |  83  |  6.9 | 81   | 8    |  1   | \n| 94 |  9   |  24  | 13.8 | 81   | 8    |  2   | \n| 95 | 16   |  77  |  7.4 | 82   | 8    |  3   | \n| 97 | 35   |  NA  |  7.4 | 85   | 8    |  5   | \n| 102 | NA   | 222  |  8.6 | 92   | 8    | 10   | \n| 103 | NA   | 137  | 11.5 | 86   | 8    | 11   | \n| 104 | 44   | 192  | 11.5 | 86   | 8    | 12   | \n| 105 | 28   | 273  | 11.5 | 82   | 8    | 13   | \n| 107 | NA   |  64  | 11.5 | 79   | 8    | 15   | \n| 108 | 22   |  71  | 10.3 | 77   | 8    | 16   | \n| 109 | 59   |  51  |  6.3 | 79   | 8    | 17   | \n| 110 | 23   | 115  |  7.4 | 76   | 8    | 18   | \n| 111 | 31   | 244  | 10.9 | 78   | 8    | 19   | \n\n\n",
   "text/plain": "    Ozone Solar.R Wind Temp Month Day\n1   41    190      7.4 67   5      1 \n2   36    118      8.0 72   5      2 \n3   12    149     12.6 74   5      3 \n4   18    313     11.5 62   5      4 \n5   NA     NA     14.3 56   5      5 \n6   28     NA     14.9 66   5      6 \n7   23    299      8.6 65   5      7 \n8   19     99     13.8 59   5      8 \n9    8     19     20.1 61   5      9 \n10  NA    194      8.6 69   5     10 \n11   7     NA      6.9 74   5     11 \n12  16    256      9.7 69   5     12 \n13  11    290      9.2 66   5     13 \n14  14    274     10.9 68   5     14 \n15  18     65     13.2 58   5     15 \n16  14    334     11.5 64   5     16 \n17  34    307     12.0 66   5     17 \n18   6     78     18.4 57   5     18 \n19  30    322     11.5 68   5     19 \n20  11     44      9.7 62   5     20 \n21   1      8      9.7 59   5     21 \n22  11    320     16.6 73   5     22 \n23   4     25      9.7 61   5     23 \n24  32     92     12.0 61   5     24 \n25  NA     66     16.6 57   5     25 \n27  NA     NA      8.0 57   5     27 \n28  23     13     12.0 67   5     28 \n29  45    252     14.9 81   5     29 \n31  37    279      7.4 76   5     31 \n32  NA    286      8.6 78   6      1 \n... ...   ...     ...  ...  ...   ...\n60  NA     31     14.9 77   6     29 \n61  NA    138      8.0 83   6     30 \n63  49    248      9.2 85   7      2 \n64  32    236      9.2 81   7      3 \n67  40    314     10.9 83   7      6 \n72  NA    139      8.6 82   7     11 \n73  10    264     14.3 73   7     12 \n74  27    175     14.9 81   7     13 \n75  NA    291     14.9 91   7     14 \n76   7     48     14.3 80   7     15 \n77  48    260      6.9 81   7     16 \n78  35    274     10.3 82   7     17 \n82  16      7      6.9 74   7     21 \n87  20     81      8.6 82   7     26 \n88  52     82     12.0 86   7     27 \n90  50    275      7.4 86   7     29 \n92  59    254      9.2 81   7     31 \n93  39     83      6.9 81   8      1 \n94   9     24     13.8 81   8      2 \n95  16     77      7.4 82   8      3 \n97  35     NA      7.4 85   8      5 \n102 NA    222      8.6 92   8     10 \n103 NA    137     11.5 86   8     11 \n104 44    192     11.5 86   8     12 \n105 28    273     11.5 82   8     13 \n107 NA     64     11.5 79   8     15 \n108 22     71     10.3 77   8     16 \n109 59     51      6.3 79   8     17 \n110 23    115      7.4 76   8     18 \n111 31    244     10.9 78   8     19 "
  },
  "metadata": {},
  "output_type": "display_data"
 }
]
```

```{.python .input  n=35}
#export and save the result into working directory with file name as goodquality.txt
write.table(airquality[goodindices1,], "goodquality.txt", sep=",")
```

```{.python .input  n=36}
# check whether the file exported into working directory
list.files() 
```

```{.json .output n=36}
[
 {
  "data": {
   "text/html": "<ol class=list-inline>\n\t<li>'Data Science Process.pdf'</li>\n\t<li>'goodquality.txt'</li>\n\t<li>'README.md'</li>\n\t<li>'sphweb_Stats.ipynb'</li>\n</ol>\n",
   "text/latex": "\\begin{enumerate*}\n\\item 'Data Science Process.pdf'\n\\item 'goodquality.txt'\n\\item 'README.md'\n\\item 'sphweb\\_Stats.ipynb'\n\\end{enumerate*}\n",
   "text/markdown": "1. 'Data Science Process.pdf'\n2. 'goodquality.txt'\n3. 'README.md'\n4. 'sphweb_Stats.ipynb'\n\n\n",
   "text/plain": "[1] \"Data Science Process.pdf\" \"goodquality.txt\"         \n[3] \"README.md\"                \"sphweb_Stats.ipynb\"      "
  },
  "metadata": {},
  "output_type": "display_data"
 }
]
```

```{.python .input  n=37}
#open the file and check the data
file.edit('goodquality.txt')
```

### To open a pdf file from working directory using package from bioconductor (
general topic) 
Use the biocLite.R script to install Bioconductor packages.
To install core packages, type the following in an R command window:


```R
source("https://bioconductor.org/biocLite.R")
biocLite("Biobase")
#to
install packages from bioconductor
#try http:// if https:// URLs are not
supported
```

```{.python .input  n=38}
library(Biobase)
openPDF("Data Science Process.pdf") 
```

```{.json .output n=38}
[
 {
  "name": "stderr",
  "output_type": "stream",
  "text": "Loading required package: BiocGenerics\nLoading required package: parallel\n\nAttaching package: 'BiocGenerics'\n\nThe following objects are masked from 'package:parallel':\n\n    clusterApply, clusterApplyLB, clusterCall, clusterEvalQ,\n    clusterExport, clusterMap, parApply, parCapply, parLapply,\n    parLapplyLB, parRapply, parSapply, parSapplyLB\n\nThe following objects are masked from 'package:stats':\n\n    IQR, mad, xtabs\n\nThe following objects are masked from 'package:base':\n\n    anyDuplicated, append, as.data.frame, cbind, colnames, do.call,\n    duplicated, eval, evalq, Filter, Find, get, grep, grepl, intersect,\n    is.unsorted, lapply, lengths, Map, mapply, match, mget, order,\n    paste, pmax, pmax.int, pmin, pmin.int, Position, rank, rbind,\n    Reduce, rownames, sapply, setdiff, sort, table, tapply, union,\n    unique, unsplit\n\nWelcome to Bioconductor\n\n    Vignettes contain introductory material; view with\n    'browseVignettes()'. To cite Bioconductor, see\n    'citation(\"Biobase\")', and for packages 'citation(\"pkgname\")'.\n\n"
 },
 {
  "data": {
   "text/html": "TRUE",
   "text/latex": "TRUE",
   "text/markdown": "TRUE",
   "text/plain": "[1] TRUE"
  },
  "metadata": {},
  "output_type": "display_data"
 }
]
```

### While Statements & REPEAT
Similar to a loop function, the while statement
can be used to perform an operation while a given condition is true.  For
example:

```{.python .input  n=39}
z <- 0

while (z < 5) {
    
    z <- z + 2
    
    print(z)
    
}
```

```{.json .output n=39}
[
 {
  "name": "stdout",
  "output_type": "stream",
  "text": "[1] 2\n[1] 4\n[1] 6\n"
 }
]
```

In the above while statement we initiate z to have a value of 0.  We then state
that as long as z is less than 5 we will continue to perform the following loop
operation z<-z+2.
Thus we have
```R
z <- 0+2  ##Initially z is 0, but after the
first iteration of the loop the value of z is 2

z <- 2+2  ## After the second
iteration the value of z is 4

z <- 4+2  ## After the third iteration the value
of z is 6
```
The while statement stops here because now z is now bigger than 5.

### repeat exercies

```{.python .input  n=40}
#Another option for looping is the repeat function. An example follows:
i<-1

repeat{

    print(i)

    if( i == 15) break

    i<-i+1

}
```

```{.json .output n=40}
[
 {
  "name": "stdout",
  "output_type": "stream",
  "text": "[1] 1\n[1] 2\n[1] 3\n[1] 4\n[1] 5\n[1] 6\n[1] 7\n[1] 8\n[1] 9\n[1] 10\n[1] 11\n[1] 12\n[1] 13\n[1] 14\n[1] 15\n"
 }
]
```

```{.python .input  n=41}
x <- 1
repeat{
    print(x)
    x <- x+1
    if (x == 6){
        break
    }
        
}
```

```{.json .output n=41}
[
 {
  "name": "stdout",
  "output_type": "stream",
  "text": "[1] 1\n[1] 2\n[1] 3\n[1] 4\n[1] 5\n"
 }
]
```

```{.python .input  n=42}
# For the first exercise, write a repeat{} loop that prints all the even numbers
# from 2 <U+0096> 10, via incrementing the variable, <U+0093>i <- 0<U+0093>.
i <- 0
repeat {
    i <- i + 2
    print(i)
    if (i == 10) 
        break
}
```

```{.json .output n=42}
[
 {
  "name": "stdout",
  "output_type": "stream",
  "text": "[1] 2\n[1] 4\n[1] 6\n[1] 8\n[1] 10\n"
 }
]
```

#Using the following variables: 
```R 
msg <- c('Hello') 
i <- 1 
``` 
Write a
repeat{} loop that breaks off the incrementation of, i, after 5 loops, andz
prints msg at every increment.

```{.python .input  n=43}
msg <- c("Hello")
i <- 1

repeat {
  i <- i + 1
    print(msg)
    if (i == 5) {break}        
}
```

```{.json .output n=43}
[
 {
  "name": "stdout",
  "output_type": "stream",
  "text": "[1] \"Hello\"\n[1] \"Hello\"\n[1] \"Hello\"\n[1] \"Hello\"\n"
 }
]
```

```{.python .input  n=44}
msg <- c('Hello')
i <- 1 
repeat{
print(msg)
i <- i +1
if (i == 5)break
    }
```

```{.json .output n=44}
[
 {
  "name": "stdout",
  "output_type": "stream",
  "text": "[1] \"Hello\"\n[1] \"Hello\"\n[1] \"Hello\"\n[1] \"Hello\"\n"
 }
]
```

### while exercises

```{.python .input  n=45}
#With, i <- 1, write a while() loop that prints the odd numbers from 1 through 7.
i <- 1
while(i<=7){
    print(i)
    i <- i +2    
}
```

```{.json .output n=45}
[
 {
  "name": "stdout",
  "output_type": "stream",
  "text": "[1] 1\n[1] 3\n[1] 5\n[1] 7\n"
 }
]
```

```{.python .input  n=46}
#Write a while() loop that increments the variable, “i“, 6 times, and prints “msg” at every iteration.
i <- 1
while(i<=6){
    print(msg)
    i <- i +1
}


```

```{.json .output n=46}
[
 {
  "name": "stdout",
  "output_type": "stream",
  "text": "[1] \"Hello\"\n[1] \"Hello\"\n[1] \"Hello\"\n[1] \"Hello\"\n[1] \"Hello\"\n[1] \"Hello\"\n"
 }
]
```

### for loop exercises

#### examples:
```R
for(i in 1:4) {
print("variable"[i])
}
```

```{.python .input  n=47}
a <- c(15,23,78,45,124,82,75)
for (i in 1:4){
    print(a[i])
}
```

```{.json .output n=47}
[
 {
  "name": "stdout",
  "output_type": "stream",
  "text": "[1] 15\n[1] 23\n[1] 78\n[1] 45\n"
 }
]
```

```R
for(i in seq("variable")) {
print(i)
}
```

```{.python .input  n=48}
for (i in seq(a)){
    print(i)
}
```

```{.json .output n=48}
[
 {
  "name": "stdout",
  "output_type": "stream",
  "text": "[1] 1\n[1] 2\n[1] 3\n[1] 4\n[1] 5\n[1] 6\n[1] 7\n"
 }
]
```

```R
for(i in seq_along("variable")) {
print("variable"[i])
}
```

```{.python .input  n=49}
for (i in seq_along(a)){
    print(a[i])
}
```

```{.json .output n=49}
[
 {
  "name": "stdout",
  "output_type": "stream",
  "text": "[1] 15\n[1] 23\n[1] 78\n[1] 45\n[1] 124\n[1] 82\n[1] 75\n"
 }
]
```

```R
for(letter in "variable") {
print(letter)
```

```{.python .input  n=50}
a <- "Last Checkpoint: 16 hours ago (unsaved changes)"
for (letter in 2){
    print(letter)
}
```

```{.json .output n=50}
[
 {
  "name": "stdout",
  "output_type": "stream",
  "text": "[1] 2\n"
 }
]
```

```{.python .input  n=51}
 # Create a vector filled with random normal values
u1 <- rnorm(30)
print("This loop calculates the square of the first 10 elements of vector u1")

# Initialize `usq`
usq <- 0

for(i in 1:10) {
  # i-th element of `u1` squared into `i`-th position of `usq`
  usq[i] <- u1[i]*u1[i]
  print(usq[i])
}

print(i)
```

```{.json .output n=51}
[
 {
  "name": "stdout",
  "output_type": "stream",
  "text": "[1] \"This loop calculates the square of the first 10 elements of vector u1\"\n[1] 1.43012\n[1] 2.745953\n[1] 3.828834\n[1] 0.1054617\n[1] 0.09555382\n[1] 0.03084824\n[1] 0.1164285\n[1] 2.885821\n[1] 1.421933\n[1] 0.04931634\n[1] 10\n"
 }
]
```

### Conditional Indexing
Data frames and matrices allow for conditional indexing
in R, which is often very useful. Instead of creating the goodair vector using a
loop, we could directly extract the good air quality days using conditional
indexing, using the single command below:

```{.python .input  n=52}
airqualfull[airqualfull$Ozone < 60,]
```

```{.json .output n=52}
[
 {
  "data": {
   "text/html": "<table>\n<thead><tr><th></th><th scope=col>Ozone</th><th scope=col>Solar.R</th><th scope=col>Wind</th><th scope=col>Temp</th><th scope=col>Month</th><th scope=col>Day</th></tr></thead>\n<tbody>\n\t<tr><th scope=row>1</th><td>41  </td><td>190 </td><td> 7.4</td><td>67  </td><td>5   </td><td> 1  </td></tr>\n\t<tr><th scope=row>2</th><td>36  </td><td>118 </td><td> 8.0</td><td>72  </td><td>5   </td><td> 2  </td></tr>\n\t<tr><th scope=row>3</th><td>12  </td><td>149 </td><td>12.6</td><td>74  </td><td>5   </td><td> 3  </td></tr>\n\t<tr><th scope=row>4</th><td>18  </td><td>313 </td><td>11.5</td><td>62  </td><td>5   </td><td> 4  </td></tr>\n\t<tr><th scope=row>7</th><td>23  </td><td>299 </td><td> 8.6</td><td>65  </td><td>5   </td><td> 7  </td></tr>\n\t<tr><th scope=row>8</th><td>19  </td><td> 99 </td><td>13.8</td><td>59  </td><td>5   </td><td> 8  </td></tr>\n\t<tr><th scope=row>9</th><td> 8  </td><td> 19 </td><td>20.1</td><td>61  </td><td>5   </td><td> 9  </td></tr>\n\t<tr><th scope=row>12</th><td>16  </td><td>256 </td><td> 9.7</td><td>69  </td><td>5   </td><td>12  </td></tr>\n\t<tr><th scope=row>13</th><td>11  </td><td>290 </td><td> 9.2</td><td>66  </td><td>5   </td><td>13  </td></tr>\n\t<tr><th scope=row>14</th><td>14  </td><td>274 </td><td>10.9</td><td>68  </td><td>5   </td><td>14  </td></tr>\n\t<tr><th scope=row>15</th><td>18  </td><td> 65 </td><td>13.2</td><td>58  </td><td>5   </td><td>15  </td></tr>\n\t<tr><th scope=row>16</th><td>14  </td><td>334 </td><td>11.5</td><td>64  </td><td>5   </td><td>16  </td></tr>\n\t<tr><th scope=row>17</th><td>34  </td><td>307 </td><td>12.0</td><td>66  </td><td>5   </td><td>17  </td></tr>\n\t<tr><th scope=row>18</th><td> 6  </td><td> 78 </td><td>18.4</td><td>57  </td><td>5   </td><td>18  </td></tr>\n\t<tr><th scope=row>19</th><td>30  </td><td>322 </td><td>11.5</td><td>68  </td><td>5   </td><td>19  </td></tr>\n\t<tr><th scope=row>20</th><td>11  </td><td> 44 </td><td> 9.7</td><td>62  </td><td>5   </td><td>20  </td></tr>\n\t<tr><th scope=row>21</th><td> 1  </td><td>  8 </td><td> 9.7</td><td>59  </td><td>5   </td><td>21  </td></tr>\n\t<tr><th scope=row>22</th><td>11  </td><td>320 </td><td>16.6</td><td>73  </td><td>5   </td><td>22  </td></tr>\n\t<tr><th scope=row>23</th><td> 4  </td><td> 25 </td><td> 9.7</td><td>61  </td><td>5   </td><td>23  </td></tr>\n\t<tr><th scope=row>24</th><td>32  </td><td> 92 </td><td>12.0</td><td>61  </td><td>5   </td><td>24  </td></tr>\n\t<tr><th scope=row>28</th><td>23  </td><td> 13 </td><td>12.0</td><td>67  </td><td>5   </td><td>28  </td></tr>\n\t<tr><th scope=row>29</th><td>45  </td><td>252 </td><td>14.9</td><td>81  </td><td>5   </td><td>29  </td></tr>\n\t<tr><th scope=row>31</th><td>37  </td><td>279 </td><td> 7.4</td><td>76  </td><td>5   </td><td>31  </td></tr>\n\t<tr><th scope=row>38</th><td>29  </td><td>127 </td><td> 9.7</td><td>82  </td><td>6   </td><td> 7  </td></tr>\n\t<tr><th scope=row>41</th><td>39  </td><td>323 </td><td>11.5</td><td>87  </td><td>6   </td><td>10  </td></tr>\n\t<tr><th scope=row>44</th><td>23  </td><td>148 </td><td> 8.0</td><td>82  </td><td>6   </td><td>13  </td></tr>\n\t<tr><th scope=row>47</th><td>21  </td><td>191 </td><td>14.9</td><td>77  </td><td>6   </td><td>16  </td></tr>\n\t<tr><th scope=row>48</th><td>37  </td><td>284 </td><td>20.7</td><td>72  </td><td>6   </td><td>17  </td></tr>\n\t<tr><th scope=row>49</th><td>20  </td><td> 37 </td><td> 9.2</td><td>65  </td><td>6   </td><td>18  </td></tr>\n\t<tr><th scope=row>50</th><td>12  </td><td>120 </td><td>11.5</td><td>73  </td><td>6   </td><td>19  </td></tr>\n\t<tr><th scope=row>...</th><td>...</td><td>...</td><td>...</td><td>...</td><td>...</td><td>...</td></tr>\n\t<tr><th scope=row>111</th><td>31  </td><td>244 </td><td>10.9</td><td>78  </td><td>8   </td><td>19  </td></tr>\n\t<tr><th scope=row>112</th><td>44  </td><td>190 </td><td>10.3</td><td>78  </td><td>8   </td><td>20  </td></tr>\n\t<tr><th scope=row>113</th><td>21  </td><td>259 </td><td>15.5</td><td>77  </td><td>8   </td><td>21  </td></tr>\n\t<tr><th scope=row>114</th><td> 9  </td><td> 36 </td><td>14.3</td><td>72  </td><td>8   </td><td>22  </td></tr>\n\t<tr><th scope=row>116</th><td>45  </td><td>212 </td><td> 9.7</td><td>79  </td><td>8   </td><td>24  </td></tr>\n\t<tr><th scope=row>128</th><td>47  </td><td> 95 </td><td> 7.4</td><td>87  </td><td>9   </td><td> 5  </td></tr>\n\t<tr><th scope=row>129</th><td>32  </td><td> 92 </td><td>15.5</td><td>84  </td><td>9   </td><td> 6  </td></tr>\n\t<tr><th scope=row>130</th><td>20  </td><td>252 </td><td>10.9</td><td>80  </td><td>9   </td><td> 7  </td></tr>\n\t<tr><th scope=row>131</th><td>23  </td><td>220 </td><td>10.3</td><td>78  </td><td>9   </td><td> 8  </td></tr>\n\t<tr><th scope=row>132</th><td>21  </td><td>230 </td><td>10.9</td><td>75  </td><td>9   </td><td> 9  </td></tr>\n\t<tr><th scope=row>133</th><td>24  </td><td>259 </td><td> 9.7</td><td>73  </td><td>9   </td><td>10  </td></tr>\n\t<tr><th scope=row>134</th><td>44  </td><td>236 </td><td>14.9</td><td>81  </td><td>9   </td><td>11  </td></tr>\n\t<tr><th scope=row>135</th><td>21  </td><td>259 </td><td>15.5</td><td>76  </td><td>9   </td><td>12  </td></tr>\n\t<tr><th scope=row>136</th><td>28  </td><td>238 </td><td> 6.3</td><td>77  </td><td>9   </td><td>13  </td></tr>\n\t<tr><th scope=row>137</th><td> 9  </td><td> 24 </td><td>10.9</td><td>71  </td><td>9   </td><td>14  </td></tr>\n\t<tr><th scope=row>138</th><td>13  </td><td>112 </td><td>11.5</td><td>71  </td><td>9   </td><td>15  </td></tr>\n\t<tr><th scope=row>139</th><td>46  </td><td>237 </td><td> 6.9</td><td>78  </td><td>9   </td><td>16  </td></tr>\n\t<tr><th scope=row>140</th><td>18  </td><td>224 </td><td>13.8</td><td>67  </td><td>9   </td><td>17  </td></tr>\n\t<tr><th scope=row>141</th><td>13  </td><td> 27 </td><td>10.3</td><td>76  </td><td>9   </td><td>18  </td></tr>\n\t<tr><th scope=row>142</th><td>24  </td><td>238 </td><td>10.3</td><td>68  </td><td>9   </td><td>19  </td></tr>\n\t<tr><th scope=row>143</th><td>16  </td><td>201 </td><td> 8.0</td><td>82  </td><td>9   </td><td>20  </td></tr>\n\t<tr><th scope=row>144</th><td>13  </td><td>238 </td><td>12.6</td><td>64  </td><td>9   </td><td>21  </td></tr>\n\t<tr><th scope=row>145</th><td>23  </td><td> 14 </td><td> 9.2</td><td>71  </td><td>9   </td><td>22  </td></tr>\n\t<tr><th scope=row>146</th><td>36  </td><td>139 </td><td>10.3</td><td>81  </td><td>9   </td><td>23  </td></tr>\n\t<tr><th scope=row>147</th><td> 7  </td><td> 49 </td><td>10.3</td><td>69  </td><td>9   </td><td>24  </td></tr>\n\t<tr><th scope=row>148</th><td>14  </td><td> 20 </td><td>16.6</td><td>63  </td><td>9   </td><td>25  </td></tr>\n\t<tr><th scope=row>149</th><td>30  </td><td>193 </td><td> 6.9</td><td>70  </td><td>9   </td><td>26  </td></tr>\n\t<tr><th scope=row>151</th><td>14  </td><td>191 </td><td>14.3</td><td>75  </td><td>9   </td><td>28  </td></tr>\n\t<tr><th scope=row>152</th><td>18  </td><td>131 </td><td> 8.0</td><td>76  </td><td>9   </td><td>29  </td></tr>\n\t<tr><th scope=row>153</th><td>20  </td><td>223 </td><td>11.5</td><td>68  </td><td>9   </td><td>30  </td></tr>\n</tbody>\n</table>\n",
   "text/latex": "\\begin{tabular}{r|llllll}\n  & Ozone & Solar.R & Wind & Temp & Month & Day\\\\\n\\hline\n\t1 & 41   & 190  &  7.4 & 67   & 5    &  1  \\\\\n\t2 & 36   & 118  &  8.0 & 72   & 5    &  2  \\\\\n\t3 & 12   & 149  & 12.6 & 74   & 5    &  3  \\\\\n\t4 & 18   & 313  & 11.5 & 62   & 5    &  4  \\\\\n\t7 & 23   & 299  &  8.6 & 65   & 5    &  7  \\\\\n\t8 & 19   &  99  & 13.8 & 59   & 5    &  8  \\\\\n\t9 &  8   &  19  & 20.1 & 61   & 5    &  9  \\\\\n\t12 & 16   & 256  &  9.7 & 69   & 5    & 12  \\\\\n\t13 & 11   & 290  &  9.2 & 66   & 5    & 13  \\\\\n\t14 & 14   & 274  & 10.9 & 68   & 5    & 14  \\\\\n\t15 & 18   &  65  & 13.2 & 58   & 5    & 15  \\\\\n\t16 & 14   & 334  & 11.5 & 64   & 5    & 16  \\\\\n\t17 & 34   & 307  & 12.0 & 66   & 5    & 17  \\\\\n\t18 &  6   &  78  & 18.4 & 57   & 5    & 18  \\\\\n\t19 & 30   & 322  & 11.5 & 68   & 5    & 19  \\\\\n\t20 & 11   &  44  &  9.7 & 62   & 5    & 20  \\\\\n\t21 &  1   &   8  &  9.7 & 59   & 5    & 21  \\\\\n\t22 & 11   & 320  & 16.6 & 73   & 5    & 22  \\\\\n\t23 &  4   &  25  &  9.7 & 61   & 5    & 23  \\\\\n\t24 & 32   &  92  & 12.0 & 61   & 5    & 24  \\\\\n\t28 & 23   &  13  & 12.0 & 67   & 5    & 28  \\\\\n\t29 & 45   & 252  & 14.9 & 81   & 5    & 29  \\\\\n\t31 & 37   & 279  &  7.4 & 76   & 5    & 31  \\\\\n\t38 & 29   & 127  &  9.7 & 82   & 6    &  7  \\\\\n\t41 & 39   & 323  & 11.5 & 87   & 6    & 10  \\\\\n\t44 & 23   & 148  &  8.0 & 82   & 6    & 13  \\\\\n\t47 & 21   & 191  & 14.9 & 77   & 6    & 16  \\\\\n\t48 & 37   & 284  & 20.7 & 72   & 6    & 17  \\\\\n\t49 & 20   &  37  &  9.2 & 65   & 6    & 18  \\\\\n\t50 & 12   & 120  & 11.5 & 73   & 6    & 19  \\\\\n\t... & ... & ... & ... & ... & ... & ...\\\\\n\t111 & 31   & 244  & 10.9 & 78   & 8    & 19  \\\\\n\t112 & 44   & 190  & 10.3 & 78   & 8    & 20  \\\\\n\t113 & 21   & 259  & 15.5 & 77   & 8    & 21  \\\\\n\t114 &  9   &  36  & 14.3 & 72   & 8    & 22  \\\\\n\t116 & 45   & 212  &  9.7 & 79   & 8    & 24  \\\\\n\t128 & 47   &  95  &  7.4 & 87   & 9    &  5  \\\\\n\t129 & 32   &  92  & 15.5 & 84   & 9    &  6  \\\\\n\t130 & 20   & 252  & 10.9 & 80   & 9    &  7  \\\\\n\t131 & 23   & 220  & 10.3 & 78   & 9    &  8  \\\\\n\t132 & 21   & 230  & 10.9 & 75   & 9    &  9  \\\\\n\t133 & 24   & 259  &  9.7 & 73   & 9    & 10  \\\\\n\t134 & 44   & 236  & 14.9 & 81   & 9    & 11  \\\\\n\t135 & 21   & 259  & 15.5 & 76   & 9    & 12  \\\\\n\t136 & 28   & 238  &  6.3 & 77   & 9    & 13  \\\\\n\t137 &  9   &  24  & 10.9 & 71   & 9    & 14  \\\\\n\t138 & 13   & 112  & 11.5 & 71   & 9    & 15  \\\\\n\t139 & 46   & 237  &  6.9 & 78   & 9    & 16  \\\\\n\t140 & 18   & 224  & 13.8 & 67   & 9    & 17  \\\\\n\t141 & 13   &  27  & 10.3 & 76   & 9    & 18  \\\\\n\t142 & 24   & 238  & 10.3 & 68   & 9    & 19  \\\\\n\t143 & 16   & 201  &  8.0 & 82   & 9    & 20  \\\\\n\t144 & 13   & 238  & 12.6 & 64   & 9    & 21  \\\\\n\t145 & 23   &  14  &  9.2 & 71   & 9    & 22  \\\\\n\t146 & 36   & 139  & 10.3 & 81   & 9    & 23  \\\\\n\t147 &  7   &  49  & 10.3 & 69   & 9    & 24  \\\\\n\t148 & 14   &  20  & 16.6 & 63   & 9    & 25  \\\\\n\t149 & 30   & 193  &  6.9 & 70   & 9    & 26  \\\\\n\t151 & 14   & 191  & 14.3 & 75   & 9    & 28  \\\\\n\t152 & 18   & 131  &  8.0 & 76   & 9    & 29  \\\\\n\t153 & 20   & 223  & 11.5 & 68   & 9    & 30  \\\\\n\\end{tabular}\n",
   "text/markdown": "\n| <!--/--> | Ozone | Solar.R | Wind | Temp | Month | Day | \n|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|\n| 1 | 41   | 190  |  7.4 | 67   | 5    |  1   | \n| 2 | 36   | 118  |  8.0 | 72   | 5    |  2   | \n| 3 | 12   | 149  | 12.6 | 74   | 5    |  3   | \n| 4 | 18   | 313  | 11.5 | 62   | 5    |  4   | \n| 7 | 23   | 299  |  8.6 | 65   | 5    |  7   | \n| 8 | 19   |  99  | 13.8 | 59   | 5    |  8   | \n| 9 |  8   |  19  | 20.1 | 61   | 5    |  9   | \n| 12 | 16   | 256  |  9.7 | 69   | 5    | 12   | \n| 13 | 11   | 290  |  9.2 | 66   | 5    | 13   | \n| 14 | 14   | 274  | 10.9 | 68   | 5    | 14   | \n| 15 | 18   |  65  | 13.2 | 58   | 5    | 15   | \n| 16 | 14   | 334  | 11.5 | 64   | 5    | 16   | \n| 17 | 34   | 307  | 12.0 | 66   | 5    | 17   | \n| 18 |  6   |  78  | 18.4 | 57   | 5    | 18   | \n| 19 | 30   | 322  | 11.5 | 68   | 5    | 19   | \n| 20 | 11   |  44  |  9.7 | 62   | 5    | 20   | \n| 21 |  1   |   8  |  9.7 | 59   | 5    | 21   | \n| 22 | 11   | 320  | 16.6 | 73   | 5    | 22   | \n| 23 |  4   |  25  |  9.7 | 61   | 5    | 23   | \n| 24 | 32   |  92  | 12.0 | 61   | 5    | 24   | \n| 28 | 23   |  13  | 12.0 | 67   | 5    | 28   | \n| 29 | 45   | 252  | 14.9 | 81   | 5    | 29   | \n| 31 | 37   | 279  |  7.4 | 76   | 5    | 31   | \n| 38 | 29   | 127  |  9.7 | 82   | 6    |  7   | \n| 41 | 39   | 323  | 11.5 | 87   | 6    | 10   | \n| 44 | 23   | 148  |  8.0 | 82   | 6    | 13   | \n| 47 | 21   | 191  | 14.9 | 77   | 6    | 16   | \n| 48 | 37   | 284  | 20.7 | 72   | 6    | 17   | \n| 49 | 20   |  37  |  9.2 | 65   | 6    | 18   | \n| 50 | 12   | 120  | 11.5 | 73   | 6    | 19   | \n| ... | ... | ... | ... | ... | ... | ... | \n| 111 | 31   | 244  | 10.9 | 78   | 8    | 19   | \n| 112 | 44   | 190  | 10.3 | 78   | 8    | 20   | \n| 113 | 21   | 259  | 15.5 | 77   | 8    | 21   | \n| 114 |  9   |  36  | 14.3 | 72   | 8    | 22   | \n| 116 | 45   | 212  |  9.7 | 79   | 8    | 24   | \n| 128 | 47   |  95  |  7.4 | 87   | 9    |  5   | \n| 129 | 32   |  92  | 15.5 | 84   | 9    |  6   | \n| 130 | 20   | 252  | 10.9 | 80   | 9    |  7   | \n| 131 | 23   | 220  | 10.3 | 78   | 9    |  8   | \n| 132 | 21   | 230  | 10.9 | 75   | 9    |  9   | \n| 133 | 24   | 259  |  9.7 | 73   | 9    | 10   | \n| 134 | 44   | 236  | 14.9 | 81   | 9    | 11   | \n| 135 | 21   | 259  | 15.5 | 76   | 9    | 12   | \n| 136 | 28   | 238  |  6.3 | 77   | 9    | 13   | \n| 137 |  9   |  24  | 10.9 | 71   | 9    | 14   | \n| 138 | 13   | 112  | 11.5 | 71   | 9    | 15   | \n| 139 | 46   | 237  |  6.9 | 78   | 9    | 16   | \n| 140 | 18   | 224  | 13.8 | 67   | 9    | 17   | \n| 141 | 13   |  27  | 10.3 | 76   | 9    | 18   | \n| 142 | 24   | 238  | 10.3 | 68   | 9    | 19   | \n| 143 | 16   | 201  |  8.0 | 82   | 9    | 20   | \n| 144 | 13   | 238  | 12.6 | 64   | 9    | 21   | \n| 145 | 23   |  14  |  9.2 | 71   | 9    | 22   | \n| 146 | 36   | 139  | 10.3 | 81   | 9    | 23   | \n| 147 |  7   |  49  | 10.3 | 69   | 9    | 24   | \n| 148 | 14   |  20  | 16.6 | 63   | 9    | 25   | \n| 149 | 30   | 193  |  6.9 | 70   | 9    | 26   | \n| 151 | 14   | 191  | 14.3 | 75   | 9    | 28   | \n| 152 | 18   | 131  |  8.0 | 76   | 9    | 29   | \n| 153 | 20   | 223  | 11.5 | 68   | 9    | 30   | \n\n\n",
   "text/plain": "    Ozone Solar.R Wind Temp Month Day\n1   41    190      7.4 67   5      1 \n2   36    118      8.0 72   5      2 \n3   12    149     12.6 74   5      3 \n4   18    313     11.5 62   5      4 \n7   23    299      8.6 65   5      7 \n8   19     99     13.8 59   5      8 \n9    8     19     20.1 61   5      9 \n12  16    256      9.7 69   5     12 \n13  11    290      9.2 66   5     13 \n14  14    274     10.9 68   5     14 \n15  18     65     13.2 58   5     15 \n16  14    334     11.5 64   5     16 \n17  34    307     12.0 66   5     17 \n18   6     78     18.4 57   5     18 \n19  30    322     11.5 68   5     19 \n20  11     44      9.7 62   5     20 \n21   1      8      9.7 59   5     21 \n22  11    320     16.6 73   5     22 \n23   4     25      9.7 61   5     23 \n24  32     92     12.0 61   5     24 \n28  23     13     12.0 67   5     28 \n29  45    252     14.9 81   5     29 \n31  37    279      7.4 76   5     31 \n38  29    127      9.7 82   6      7 \n41  39    323     11.5 87   6     10 \n44  23    148      8.0 82   6     13 \n47  21    191     14.9 77   6     16 \n48  37    284     20.7 72   6     17 \n49  20     37      9.2 65   6     18 \n50  12    120     11.5 73   6     19 \n... ...   ...     ...  ...  ...   ...\n111 31    244     10.9 78   8     19 \n112 44    190     10.3 78   8     20 \n113 21    259     15.5 77   8     21 \n114  9     36     14.3 72   8     22 \n116 45    212      9.7 79   8     24 \n128 47     95      7.4 87   9      5 \n129 32     92     15.5 84   9      6 \n130 20    252     10.9 80   9      7 \n131 23    220     10.3 78   9      8 \n132 21    230     10.9 75   9      9 \n133 24    259      9.7 73   9     10 \n134 44    236     14.9 81   9     11 \n135 21    259     15.5 76   9     12 \n136 28    238      6.3 77   9     13 \n137  9     24     10.9 71   9     14 \n138 13    112     11.5 71   9     15 \n139 46    237      6.9 78   9     16 \n140 18    224     13.8 67   9     17 \n141 13     27     10.3 76   9     18 \n142 24    238     10.3 68   9     19 \n143 16    201      8.0 82   9     20 \n144 13    238     12.6 64   9     21 \n145 23     14      9.2 71   9     22 \n146 36    139     10.3 81   9     23 \n147  7     49     10.3 69   9     24 \n148 14     20     16.6 63   9     25 \n149 30    193      6.9 70   9     26 \n151 14    191     14.3 75   9     28 \n152 18    131      8.0 76   9     29 \n153 20    223     11.5 68   9     30 "
  },
  "metadata": {},
  "output_type": "display_data"
 }
]
```

It is worthwhile to keep in mind that many things in R can be done avoiding
loops, and using conditional indexing can save a lot of time and effort!
However, there are other times when using loops may be the only (or best) way to
do things.

```{.python .input  n=53}
split(airqualfull$Ozone, airqualfull$Temp < 80)
```

```{.json .output n=53}
[
 {
  "data": {
   "text/html": "<dl>\n\t<dt>$`FALSE`</dt>\n\t\t<dd><ol class=list-inline>\n\t<li>45</li>\n\t<li>29</li>\n\t<li>71</li>\n\t<li>39</li>\n\t<li>23</li>\n\t<li>135</li>\n\t<li>49</li>\n\t<li>32</li>\n\t<li>64</li>\n\t<li>40</li>\n\t<li>77</li>\n\t<li>97</li>\n\t<li>97</li>\n\t<li>85</li>\n\t<li>27</li>\n\t<li>7</li>\n\t<li>48</li>\n\t<li>35</li>\n\t<li>61</li>\n\t<li>79</li>\n\t<li>63</li>\n\t<li>80</li>\n\t<li>108</li>\n\t<li>20</li>\n\t<li>52</li>\n\t<li>82</li>\n\t<li>50</li>\n\t<li>64</li>\n\t<li>59</li>\n\t<li>39</li>\n\t<li>9</li>\n\t<li>16</li>\n\t<li>122</li>\n\t<li>89</li>\n\t<li>110</li>\n\t<li>44</li>\n\t<li>28</li>\n\t<li>65</li>\n\t<li>168</li>\n\t<li>73</li>\n\t<li>76</li>\n\t<li>118</li>\n\t<li>84</li>\n\t<li>85</li>\n\t<li>96</li>\n\t<li>78</li>\n\t<li>73</li>\n\t<li>91</li>\n\t<li>47</li>\n\t<li>32</li>\n\t<li>20</li>\n\t<li>44</li>\n\t<li>16</li>\n\t<li>36</li>\n</ol>\n</dd>\n\t<dt>$`TRUE`</dt>\n\t\t<dd><ol class=list-inline>\n\t<li>41</li>\n\t<li>36</li>\n\t<li>12</li>\n\t<li>18</li>\n\t<li>23</li>\n\t<li>19</li>\n\t<li>8</li>\n\t<li>16</li>\n\t<li>11</li>\n\t<li>14</li>\n\t<li>18</li>\n\t<li>14</li>\n\t<li>34</li>\n\t<li>6</li>\n\t<li>30</li>\n\t<li>11</li>\n\t<li>1</li>\n\t<li>11</li>\n\t<li>4</li>\n\t<li>32</li>\n\t<li>23</li>\n\t<li>115</li>\n\t<li>37</li>\n\t<li>21</li>\n\t<li>37</li>\n\t<li>20</li>\n\t<li>12</li>\n\t<li>13</li>\n\t<li>10</li>\n\t<li>16</li>\n\t<li>22</li>\n\t<li>59</li>\n\t<li>23</li>\n\t<li>31</li>\n\t<li>44</li>\n\t<li>21</li>\n\t<li>9</li>\n\t<li>45</li>\n\t<li>23</li>\n\t<li>21</li>\n\t<li>24</li>\n\t<li>21</li>\n\t<li>28</li>\n\t<li>9</li>\n\t<li>13</li>\n\t<li>46</li>\n\t<li>18</li>\n\t<li>13</li>\n\t<li>24</li>\n\t<li>13</li>\n\t<li>23</li>\n\t<li>7</li>\n\t<li>14</li>\n\t<li>30</li>\n\t<li>14</li>\n\t<li>18</li>\n\t<li>20</li>\n</ol>\n</dd>\n</dl>\n",
   "text/latex": "\\begin{description}\n\\item[\\$`FALSE`] \\begin{enumerate*}\n\\item 45\n\\item 29\n\\item 71\n\\item 39\n\\item 23\n\\item 135\n\\item 49\n\\item 32\n\\item 64\n\\item 40\n\\item 77\n\\item 97\n\\item 97\n\\item 85\n\\item 27\n\\item 7\n\\item 48\n\\item 35\n\\item 61\n\\item 79\n\\item 63\n\\item 80\n\\item 108\n\\item 20\n\\item 52\n\\item 82\n\\item 50\n\\item 64\n\\item 59\n\\item 39\n\\item 9\n\\item 16\n\\item 122\n\\item 89\n\\item 110\n\\item 44\n\\item 28\n\\item 65\n\\item 168\n\\item 73\n\\item 76\n\\item 118\n\\item 84\n\\item 85\n\\item 96\n\\item 78\n\\item 73\n\\item 91\n\\item 47\n\\item 32\n\\item 20\n\\item 44\n\\item 16\n\\item 36\n\\end{enumerate*}\n\n\\item[\\$`TRUE`] \\begin{enumerate*}\n\\item 41\n\\item 36\n\\item 12\n\\item 18\n\\item 23\n\\item 19\n\\item 8\n\\item 16\n\\item 11\n\\item 14\n\\item 18\n\\item 14\n\\item 34\n\\item 6\n\\item 30\n\\item 11\n\\item 1\n\\item 11\n\\item 4\n\\item 32\n\\item 23\n\\item 115\n\\item 37\n\\item 21\n\\item 37\n\\item 20\n\\item 12\n\\item 13\n\\item 10\n\\item 16\n\\item 22\n\\item 59\n\\item 23\n\\item 31\n\\item 44\n\\item 21\n\\item 9\n\\item 45\n\\item 23\n\\item 21\n\\item 24\n\\item 21\n\\item 28\n\\item 9\n\\item 13\n\\item 46\n\\item 18\n\\item 13\n\\item 24\n\\item 13\n\\item 23\n\\item 7\n\\item 14\n\\item 30\n\\item 14\n\\item 18\n\\item 20\n\\end{enumerate*}\n\n\\end{description}\n",
   "text/markdown": "$`FALSE`\n:   1. 45\n2. 29\n3. 71\n4. 39\n5. 23\n6. 135\n7. 49\n8. 32\n9. 64\n10. 40\n11. 77\n12. 97\n13. 97\n14. 85\n15. 27\n16. 7\n17. 48\n18. 35\n19. 61\n20. 79\n21. 63\n22. 80\n23. 108\n24. 20\n25. 52\n26. 82\n27. 50\n28. 64\n29. 59\n30. 39\n31. 9\n32. 16\n33. 122\n34. 89\n35. 110\n36. 44\n37. 28\n38. 65\n39. 168\n40. 73\n41. 76\n42. 118\n43. 84\n44. 85\n45. 96\n46. 78\n47. 73\n48. 91\n49. 47\n50. 32\n51. 20\n52. 44\n53. 16\n54. 36\n\n\n\n$`TRUE`\n:   1. 41\n2. 36\n3. 12\n4. 18\n5. 23\n6. 19\n7. 8\n8. 16\n9. 11\n10. 14\n11. 18\n12. 14\n13. 34\n14. 6\n15. 30\n16. 11\n17. 1\n18. 11\n19. 4\n20. 32\n21. 23\n22. 115\n23. 37\n24. 21\n25. 37\n26. 20\n27. 12\n28. 13\n29. 10\n30. 16\n31. 22\n32. 59\n33. 23\n34. 31\n35. 44\n36. 21\n37. 9\n38. 45\n39. 23\n40. 21\n41. 24\n42. 21\n43. 28\n44. 9\n45. 13\n46. 46\n47. 18\n48. 13\n49. 24\n50. 13\n51. 23\n52. 7\n53. 14\n54. 30\n55. 14\n56. 18\n57. 20\n\n\n\n\n\n",
   "text/plain": "$`FALSE`\n [1]  45  29  71  39  23 135  49  32  64  40  77  97  97  85  27   7  48  35  61\n[20]  79  63  80 108  20  52  82  50  64  59  39   9  16 122  89 110  44  28  65\n[39] 168  73  76 118  84  85  96  78  73  91  47  32  20  44  16  36\n\n$`TRUE`\n [1]  41  36  12  18  23  19   8  16  11  14  18  14  34   6  30  11   1  11   4\n[20]  32  23 115  37  21  37  20  12  13  10  16  22  59  23  31  44  21   9  45\n[39]  23  21  24  21  28   9  13  46  18  13  24  13  23   7  14  30  14  18  20\n"
  },
  "metadata": {},
  "output_type": "display_data"
 }
]
```

```{.python .input  n=54}
split(faithful$eruptions, faithful$waiting<50)
```

```{.json .output n=54}
[
 {
  "data": {
   "text/html": "<dl>\n\t<dt>$`FALSE`</dt>\n\t\t<dd><ol class=list-inline>\n\t<li>3.6</li>\n\t<li>1.8</li>\n\t<li>3.333</li>\n\t<li>2.283</li>\n\t<li>4.533</li>\n\t<li>2.883</li>\n\t<li>4.7</li>\n\t<li>3.6</li>\n\t<li>1.95</li>\n\t<li>4.35</li>\n\t<li>1.833</li>\n\t<li>3.917</li>\n\t<li>4.2</li>\n\t<li>4.7</li>\n\t<li>2.167</li>\n\t<li>1.75</li>\n\t<li>4.8</li>\n\t<li>1.6</li>\n\t<li>4.25</li>\n\t<li>1.8</li>\n\t<li>3.45</li>\n\t<li>3.067</li>\n\t<li>4.533</li>\n\t<li>3.6</li>\n\t<li>1.967</li>\n\t<li>4.083</li>\n\t<li>3.85</li>\n\t<li>4.433</li>\n\t<li>4.3</li>\n\t<li>4.467</li>\n\t<li>3.367</li>\n\t<li>4.033</li>\n\t<li>3.833</li>\n\t<li>2.017</li>\n\t<li>4.833</li>\n\t<li>1.833</li>\n\t<li>4.783</li>\n\t<li>4.35</li>\n\t<li>1.883</li>\n\t<li>4.567</li>\n\t<li>1.75</li>\n\t<li>4.533</li>\n\t<li>3.317</li>\n\t<li>3.833</li>\n\t<li>2.1</li>\n\t<li>4.633</li>\n\t<li>2</li>\n\t<li>4.8</li>\n\t<li>4.716</li>\n\t<li>1.833</li>\n\t<li>4.833</li>\n\t<li>1.733</li>\n\t<li>4.883</li>\n\t<li>3.717</li>\n\t<li>1.667</li>\n\t<li>4.567</li>\n\t<li>4.317</li>\n\t<li>2.233</li>\n\t<li>4.5</li>\n\t<li>4.8</li>\n\t<li>1.817</li>\n\t<li>4.4</li>\n\t<li>4.167</li>\n\t<li>4.7</li>\n\t<li>2.067</li>\n\t<li>4.7</li>\n\t<li>4.033</li>\n\t<li>1.967</li>\n\t<li>4.5</li>\n\t<li>4</li>\n\t<li>1.983</li>\n\t<li>5.067</li>\n\t<li>2.017</li>\n\t<li>4.567</li>\n\t<li>3.883</li>\n\t<li>3.6</li>\n\t<li>4.133</li>\n\t<li>4.333</li>\n\t<li>4.1</li>\n\t<li>2.633</li>\n\t<li>4.067</li>\n\t<li>4.933</li>\n\t<li>3.95</li>\n\t<li>4.517</li>\n\t<li>4</li>\n\t<li>2.2</li>\n\t<li>4.333</li>\n\t<li>1.867</li>\n\t<li>4.817</li>\n\t<li>1.833</li>\n\t<li>4.3</li>\n\t<li>4.667</li>\n\t<li>3.75</li>\n\t<li>1.867</li>\n\t<li>4.9</li>\n\t<li>2.483</li>\n\t<li>4.367</li>\n\t<li>4.5</li>\n\t<li>4.05</li>\n\t<li>4.7</li>\n\t<li>1.783</li>\n\t<li>4.85</li>\n\t<li>3.683</li>\n\t<li>4.733</li>\n\t<li>2.3</li>\n\t<li>4.9</li>\n\t<li>4.417</li>\n\t<li>1.7</li>\n\t<li>4.633</li>\n\t<li>2.317</li>\n\t<li>4.6</li>\n\t<li>1.817</li>\n\t<li>4.417</li>\n\t<li>2.617</li>\n\t<li>4.067</li>\n\t<li>4.25</li>\n\t<li>1.967</li>\n\t<li>4.6</li>\n\t<li>3.767</li>\n\t<li>4.5</li>\n\t<li>2.267</li>\n\t<li>4.65</li>\n\t<li>4.167</li>\n\t<li>2.8</li>\n\t<li>4.333</li>\n\t<li>4.383</li>\n\t<li>1.883</li>\n\t<li>4.933</li>\n\t<li>2.033</li>\n\t<li>3.733</li>\n\t<li>4.233</li>\n\t<li>2.233</li>\n\t<li>4.533</li>\n\t<li>4.817</li>\n\t<li>4.333</li>\n\t<li>1.983</li>\n\t<li>4.633</li>\n\t<li>5.1</li>\n\t<li>1.8</li>\n\t<li>5.033</li>\n\t<li>4</li>\n\t<li>2.4</li>\n\t<li>4.6</li>\n\t<li>3.567</li>\n\t<li>4</li>\n\t<li>4.5</li>\n\t<li>4.083</li>\n\t<li>1.8</li>\n\t<li>3.967</li>\n\t<li>4.15</li>\n\t<li>2</li>\n\t<li>3.833</li>\n\t<li>3.5</li>\n\t<li>4.583</li>\n\t<li>2.367</li>\n\t<li>5</li>\n\t<li>1.933</li>\n\t<li>4.617</li>\n\t<li>2.083</li>\n\t<li>4.583</li>\n\t<li>3.333</li>\n\t<li>4.167</li>\n\t<li>4.333</li>\n\t<li>4.5</li>\n\t<li>2.417</li>\n\t<li>4</li>\n\t<li>4.167</li>\n\t<li>1.883</li>\n\t<li>4.583</li>\n\t<li>4.25</li>\n\t<li>3.767</li>\n\t<li>2.033</li>\n\t<li>4.433</li>\n\t<li>4.083</li>\n\t<li>4.417</li>\n\t<li>2.183</li>\n\t<li>4.8</li>\n\t<li>1.833</li>\n\t<li>4.8</li>\n\t<li>4.1</li>\n\t<li>3.966</li>\n\t<li>4.233</li>\n\t<li>3.5</li>\n\t<li>4.366</li>\n\t<li>2.25</li>\n\t<li>4.667</li>\n\t<li>2.1</li>\n\t<li>4.35</li>\n\t<li>4.133</li>\n\t<li>1.867</li>\n\t<li>4.6</li>\n\t<li>4.367</li>\n\t<li>3.85</li>\n\t<li>4.5</li>\n\t<li>2.383</li>\n\t<li>4.7</li>\n\t<li>3.833</li>\n\t<li>3.417</li>\n\t<li>4.233</li>\n\t<li>2.4</li>\n\t<li>4.8</li>\n\t<li>2</li>\n\t<li>4.15</li>\n\t<li>1.867</li>\n\t<li>4.267</li>\n\t<li>1.75</li>\n\t<li>4.483</li>\n\t<li>4</li>\n\t<li>4.117</li>\n\t<li>4.083</li>\n\t<li>4.267</li>\n\t<li>3.917</li>\n\t<li>4.55</li>\n\t<li>4.083</li>\n\t<li>2.417</li>\n\t<li>4.183</li>\n\t<li>2.217</li>\n\t<li>4.45</li>\n\t<li>1.883</li>\n\t<li>1.85</li>\n\t<li>4.283</li>\n\t<li>3.95</li>\n\t<li>2.333</li>\n\t<li>4.15</li>\n\t<li>4.933</li>\n\t<li>2.9</li>\n\t<li>4.583</li>\n\t<li>3.833</li>\n\t<li>2.083</li>\n\t<li>4.367</li>\n\t<li>2.133</li>\n\t<li>4.35</li>\n\t<li>2.2</li>\n\t<li>4.45</li>\n\t<li>3.567</li>\n\t<li>4.5</li>\n\t<li>4.15</li>\n\t<li>3.817</li>\n\t<li>3.917</li>\n\t<li>4.45</li>\n\t<li>2</li>\n\t<li>4.283</li>\n\t<li>4.767</li>\n\t<li>4.533</li>\n\t<li>1.85</li>\n\t<li>4.25</li>\n\t<li>2.25</li>\n\t<li>4.75</li>\n\t<li>4.117</li>\n\t<li>4.417</li>\n\t<li>4.467</li>\n</ol>\n</dd>\n\t<dt>$`TRUE`</dt>\n\t\t<dd><ol class=list-inline>\n\t<li>1.75</li>\n\t<li>1.75</li>\n\t<li>1.867</li>\n\t<li>1.75</li>\n\t<li>2.167</li>\n\t<li>2.1</li>\n\t<li>1.867</li>\n\t<li>1.917</li>\n\t<li>1.867</li>\n\t<li>1.833</li>\n\t<li>2.017</li>\n\t<li>2.2</li>\n\t<li>1.917</li>\n\t<li>1.833</li>\n\t<li>1.783</li>\n\t<li>1.933</li>\n\t<li>1.867</li>\n\t<li>2.35</li>\n\t<li>1.983</li>\n\t<li>2.15</li>\n\t<li>1.817</li>\n</ol>\n</dd>\n</dl>\n",
   "text/latex": "\\begin{description}\n\\item[\\$`FALSE`] \\begin{enumerate*}\n\\item 3.6\n\\item 1.8\n\\item 3.333\n\\item 2.283\n\\item 4.533\n\\item 2.883\n\\item 4.7\n\\item 3.6\n\\item 1.95\n\\item 4.35\n\\item 1.833\n\\item 3.917\n\\item 4.2\n\\item 4.7\n\\item 2.167\n\\item 1.75\n\\item 4.8\n\\item 1.6\n\\item 4.25\n\\item 1.8\n\\item 3.45\n\\item 3.067\n\\item 4.533\n\\item 3.6\n\\item 1.967\n\\item 4.083\n\\item 3.85\n\\item 4.433\n\\item 4.3\n\\item 4.467\n\\item 3.367\n\\item 4.033\n\\item 3.833\n\\item 2.017\n\\item 4.833\n\\item 1.833\n\\item 4.783\n\\item 4.35\n\\item 1.883\n\\item 4.567\n\\item 1.75\n\\item 4.533\n\\item 3.317\n\\item 3.833\n\\item 2.1\n\\item 4.633\n\\item 2\n\\item 4.8\n\\item 4.716\n\\item 1.833\n\\item 4.833\n\\item 1.733\n\\item 4.883\n\\item 3.717\n\\item 1.667\n\\item 4.567\n\\item 4.317\n\\item 2.233\n\\item 4.5\n\\item 4.8\n\\item 1.817\n\\item 4.4\n\\item 4.167\n\\item 4.7\n\\item 2.067\n\\item 4.7\n\\item 4.033\n\\item 1.967\n\\item 4.5\n\\item 4\n\\item 1.983\n\\item 5.067\n\\item 2.017\n\\item 4.567\n\\item 3.883\n\\item 3.6\n\\item 4.133\n\\item 4.333\n\\item 4.1\n\\item 2.633\n\\item 4.067\n\\item 4.933\n\\item 3.95\n\\item 4.517\n\\item 4\n\\item 2.2\n\\item 4.333\n\\item 1.867\n\\item 4.817\n\\item 1.833\n\\item 4.3\n\\item 4.667\n\\item 3.75\n\\item 1.867\n\\item 4.9\n\\item 2.483\n\\item 4.367\n\\item 4.5\n\\item 4.05\n\\item 4.7\n\\item 1.783\n\\item 4.85\n\\item 3.683\n\\item 4.733\n\\item 2.3\n\\item 4.9\n\\item 4.417\n\\item 1.7\n\\item 4.633\n\\item 2.317\n\\item 4.6\n\\item 1.817\n\\item 4.417\n\\item 2.617\n\\item 4.067\n\\item 4.25\n\\item 1.967\n\\item 4.6\n\\item 3.767\n\\item 4.5\n\\item 2.267\n\\item 4.65\n\\item 4.167\n\\item 2.8\n\\item 4.333\n\\item 4.383\n\\item 1.883\n\\item 4.933\n\\item 2.033\n\\item 3.733\n\\item 4.233\n\\item 2.233\n\\item 4.533\n\\item 4.817\n\\item 4.333\n\\item 1.983\n\\item 4.633\n\\item 5.1\n\\item 1.8\n\\item 5.033\n\\item 4\n\\item 2.4\n\\item 4.6\n\\item 3.567\n\\item 4\n\\item 4.5\n\\item 4.083\n\\item 1.8\n\\item 3.967\n\\item 4.15\n\\item 2\n\\item 3.833\n\\item 3.5\n\\item 4.583\n\\item 2.367\n\\item 5\n\\item 1.933\n\\item 4.617\n\\item 2.083\n\\item 4.583\n\\item 3.333\n\\item 4.167\n\\item 4.333\n\\item 4.5\n\\item 2.417\n\\item 4\n\\item 4.167\n\\item 1.883\n\\item 4.583\n\\item 4.25\n\\item 3.767\n\\item 2.033\n\\item 4.433\n\\item 4.083\n\\item 4.417\n\\item 2.183\n\\item 4.8\n\\item 1.833\n\\item 4.8\n\\item 4.1\n\\item 3.966\n\\item 4.233\n\\item 3.5\n\\item 4.366\n\\item 2.25\n\\item 4.667\n\\item 2.1\n\\item 4.35\n\\item 4.133\n\\item 1.867\n\\item 4.6\n\\item 4.367\n\\item 3.85\n\\item 4.5\n\\item 2.383\n\\item 4.7\n\\item 3.833\n\\item 3.417\n\\item 4.233\n\\item 2.4\n\\item 4.8\n\\item 2\n\\item 4.15\n\\item 1.867\n\\item 4.267\n\\item 1.75\n\\item 4.483\n\\item 4\n\\item 4.117\n\\item 4.083\n\\item 4.267\n\\item 3.917\n\\item 4.55\n\\item 4.083\n\\item 2.417\n\\item 4.183\n\\item 2.217\n\\item 4.45\n\\item 1.883\n\\item 1.85\n\\item 4.283\n\\item 3.95\n\\item 2.333\n\\item 4.15\n\\item 4.933\n\\item 2.9\n\\item 4.583\n\\item 3.833\n\\item 2.083\n\\item 4.367\n\\item 2.133\n\\item 4.35\n\\item 2.2\n\\item 4.45\n\\item 3.567\n\\item 4.5\n\\item 4.15\n\\item 3.817\n\\item 3.917\n\\item 4.45\n\\item 2\n\\item 4.283\n\\item 4.767\n\\item 4.533\n\\item 1.85\n\\item 4.25\n\\item 2.25\n\\item 4.75\n\\item 4.117\n\\item 4.417\n\\item 4.467\n\\end{enumerate*}\n\n\\item[\\$`TRUE`] \\begin{enumerate*}\n\\item 1.75\n\\item 1.75\n\\item 1.867\n\\item 1.75\n\\item 2.167\n\\item 2.1\n\\item 1.867\n\\item 1.917\n\\item 1.867\n\\item 1.833\n\\item 2.017\n\\item 2.2\n\\item 1.917\n\\item 1.833\n\\item 1.783\n\\item 1.933\n\\item 1.867\n\\item 2.35\n\\item 1.983\n\\item 2.15\n\\item 1.817\n\\end{enumerate*}\n\n\\end{description}\n",
   "text/markdown": "$`FALSE`\n:   1. 3.6\n2. 1.8\n3. 3.333\n4. 2.283\n5. 4.533\n6. 2.883\n7. 4.7\n8. 3.6\n9. 1.95\n10. 4.35\n11. 1.833\n12. 3.917\n13. 4.2\n14. 4.7\n15. 2.167\n16. 1.75\n17. 4.8\n18. 1.6\n19. 4.25\n20. 1.8\n21. 3.45\n22. 3.067\n23. 4.533\n24. 3.6\n25. 1.967\n26. 4.083\n27. 3.85\n28. 4.433\n29. 4.3\n30. 4.467\n31. 3.367\n32. 4.033\n33. 3.833\n34. 2.017\n35. 4.833\n36. 1.833\n37. 4.783\n38. 4.35\n39. 1.883\n40. 4.567\n41. 1.75\n42. 4.533\n43. 3.317\n44. 3.833\n45. 2.1\n46. 4.633\n47. 2\n48. 4.8\n49. 4.716\n50. 1.833\n51. 4.833\n52. 1.733\n53. 4.883\n54. 3.717\n55. 1.667\n56. 4.567\n57. 4.317\n58. 2.233\n59. 4.5\n60. 4.8\n61. 1.817\n62. 4.4\n63. 4.167\n64. 4.7\n65. 2.067\n66. 4.7\n67. 4.033\n68. 1.967\n69. 4.5\n70. 4\n71. 1.983\n72. 5.067\n73. 2.017\n74. 4.567\n75. 3.883\n76. 3.6\n77. 4.133\n78. 4.333\n79. 4.1\n80. 2.633\n81. 4.067\n82. 4.933\n83. 3.95\n84. 4.517\n85. 4\n86. 2.2\n87. 4.333\n88. 1.867\n89. 4.817\n90. 1.833\n91. 4.3\n92. 4.667\n93. 3.75\n94. 1.867\n95. 4.9\n96. 2.483\n97. 4.367\n98. 4.5\n99. 4.05\n100. 4.7\n101. 1.783\n102. 4.85\n103. 3.683\n104. 4.733\n105. 2.3\n106. 4.9\n107. 4.417\n108. 1.7\n109. 4.633\n110. 2.317\n111. 4.6\n112. 1.817\n113. 4.417\n114. 2.617\n115. 4.067\n116. 4.25\n117. 1.967\n118. 4.6\n119. 3.767\n120. 4.5\n121. 2.267\n122. 4.65\n123. 4.167\n124. 2.8\n125. 4.333\n126. 4.383\n127. 1.883\n128. 4.933\n129. 2.033\n130. 3.733\n131. 4.233\n132. 2.233\n133. 4.533\n134. 4.817\n135. 4.333\n136. 1.983\n137. 4.633\n138. 5.1\n139. 1.8\n140. 5.033\n141. 4\n142. 2.4\n143. 4.6\n144. 3.567\n145. 4\n146. 4.5\n147. 4.083\n148. 1.8\n149. 3.967\n150. 4.15\n151. 2\n152. 3.833\n153. 3.5\n154. 4.583\n155. 2.367\n156. 5\n157. 1.933\n158. 4.617\n159. 2.083\n160. 4.583\n161. 3.333\n162. 4.167\n163. 4.333\n164. 4.5\n165. 2.417\n166. 4\n167. 4.167\n168. 1.883\n169. 4.583\n170. 4.25\n171. 3.767\n172. 2.033\n173. 4.433\n174. 4.083\n175. 4.417\n176. 2.183\n177. 4.8\n178. 1.833\n179. 4.8\n180. 4.1\n181. 3.966\n182. 4.233\n183. 3.5\n184. 4.366\n185. 2.25\n186. 4.667\n187. 2.1\n188. 4.35\n189. 4.133\n190. 1.867\n191. 4.6\n192. 4.367\n193. 3.85\n194. 4.5\n195. 2.383\n196. 4.7\n197. 3.833\n198. 3.417\n199. 4.233\n200. 2.4\n201. 4.8\n202. 2\n203. 4.15\n204. 1.867\n205. 4.267\n206. 1.75\n207. 4.483\n208. 4\n209. 4.117\n210. 4.083\n211. 4.267\n212. 3.917\n213. 4.55\n214. 4.083\n215. 2.417\n216. 4.183\n217. 2.217\n218. 4.45\n219. 1.883\n220. 1.85\n221. 4.283\n222. 3.95\n223. 2.333\n224. 4.15\n225. 4.933\n226. 2.9\n227. 4.583\n228. 3.833\n229. 2.083\n230. 4.367\n231. 2.133\n232. 4.35\n233. 2.2\n234. 4.45\n235. 3.567\n236. 4.5\n237. 4.15\n238. 3.817\n239. 3.917\n240. 4.45\n241. 2\n242. 4.283\n243. 4.767\n244. 4.533\n245. 1.85\n246. 4.25\n247. 2.25\n248. 4.75\n249. 4.117\n250. 4.417\n251. 4.467\n\n\n\n$`TRUE`\n:   1. 1.75\n2. 1.75\n3. 1.867\n4. 1.75\n5. 2.167\n6. 2.1\n7. 1.867\n8. 1.917\n9. 1.867\n10. 1.833\n11. 2.017\n12. 2.2\n13. 1.917\n14. 1.833\n15. 1.783\n16. 1.933\n17. 1.867\n18. 2.35\n19. 1.983\n20. 2.15\n21. 1.817\n\n\n\n\n\n",
   "text/plain": "$`FALSE`\n  [1] 3.600 1.800 3.333 2.283 4.533 2.883 4.700 3.600 1.950 4.350 1.833 3.917\n [13] 4.200 4.700 2.167 1.750 4.800 1.600 4.250 1.800 3.450 3.067 4.533 3.600\n [25] 1.967 4.083 3.850 4.433 4.300 4.467 3.367 4.033 3.833 2.017 4.833 1.833\n [37] 4.783 4.350 1.883 4.567 1.750 4.533 3.317 3.833 2.100 4.633 2.000 4.800\n [49] 4.716 1.833 4.833 1.733 4.883 3.717 1.667 4.567 4.317 2.233 4.500 4.800\n [61] 1.817 4.400 4.167 4.700 2.067 4.700 4.033 1.967 4.500 4.000 1.983 5.067\n [73] 2.017 4.567 3.883 3.600 4.133 4.333 4.100 2.633 4.067 4.933 3.950 4.517\n [85] 4.000 2.200 4.333 1.867 4.817 1.833 4.300 4.667 3.750 1.867 4.900 2.483\n [97] 4.367 4.500 4.050 4.700 1.783 4.850 3.683 4.733 2.300 4.900 4.417 1.700\n[109] 4.633 2.317 4.600 1.817 4.417 2.617 4.067 4.250 1.967 4.600 3.767 4.500\n[121] 2.267 4.650 4.167 2.800 4.333 4.383 1.883 4.933 2.033 3.733 4.233 2.233\n[133] 4.533 4.817 4.333 1.983 4.633 5.100 1.800 5.033 4.000 2.400 4.600 3.567\n[145] 4.000 4.500 4.083 1.800 3.967 4.150 2.000 3.833 3.500 4.583 2.367 5.000\n[157] 1.933 4.617 2.083 4.583 3.333 4.167 4.333 4.500 2.417 4.000 4.167 1.883\n[169] 4.583 4.250 3.767 2.033 4.433 4.083 4.417 2.183 4.800 1.833 4.800 4.100\n[181] 3.966 4.233 3.500 4.366 2.250 4.667 2.100 4.350 4.133 1.867 4.600 4.367\n[193] 3.850 4.500 2.383 4.700 3.833 3.417 4.233 2.400 4.800 2.000 4.150 1.867\n[205] 4.267 1.750 4.483 4.000 4.117 4.083 4.267 3.917 4.550 4.083 2.417 4.183\n[217] 2.217 4.450 1.883 1.850 4.283 3.950 2.333 4.150 4.933 2.900 4.583 3.833\n[229] 2.083 4.367 2.133 4.350 2.200 4.450 3.567 4.500 4.150 3.817 3.917 4.450\n[241] 2.000 4.283 4.767 4.533 1.850 4.250 2.250 4.750 4.117 4.417 4.467\n\n$`TRUE`\n [1] 1.750 1.750 1.867 1.750 2.167 2.100 1.867 1.917 1.867 1.833 2.017 2.200\n[13] 1.917 1.833 1.783 1.933 1.867 2.350 1.983 2.150 1.817\n"
  },
  "metadata": {},
  "output_type": "display_data"
 }
]
```

### Merging and Sorting Dataframes

```{.python .input  n=55}
# you have two datasets and you want to merge them based on an ID number. A
# simple example of merging these by variable ID follows:
dataset.1 <- matrix(c(1, 13, 12, 1, 2, 12, 10, 2, 3, 13, 9, 1, 4, 9, 8, 2, 5, 3, 
    7, 3, 6, 5, 6, 1, 7, 6, 5, 2, 8, 5, 5, 3), ncol = 4, byrow = T)
dataset.2 <- matrix(c(1, 12, 2, 13, 3, 3, 4, 15, 5, 31, 6, 15, 7, 4, 8, 6), ncol = 2, 
    byrow = T)
```

```{.python .input  n=56}
class(dataset.1) #first time runs it returns  as  matrix
dataset.1<-data.frame(dataset.1)
class(dataset.1)
names(dataset.1)<-c("ID","read 1","read 2","read 3") #assign names
dataset.1
```

```{.json .output n=56}
[
 {
  "data": {
   "text/html": "'matrix'",
   "text/latex": "'matrix'",
   "text/markdown": "'matrix'",
   "text/plain": "[1] \"matrix\""
  },
  "metadata": {},
  "output_type": "display_data"
 },
 {
  "data": {
   "text/html": "'data.frame'",
   "text/latex": "'data.frame'",
   "text/markdown": "'data.frame'",
   "text/plain": "[1] \"data.frame\""
  },
  "metadata": {},
  "output_type": "display_data"
 },
 {
  "data": {
   "text/html": "<table>\n<thead><tr><th scope=col>ID</th><th scope=col>read 1</th><th scope=col>read 2</th><th scope=col>read 3</th></tr></thead>\n<tbody>\n\t<tr><td>1 </td><td>13</td><td>12</td><td>1 </td></tr>\n\t<tr><td>2 </td><td>12</td><td>10</td><td>2 </td></tr>\n\t<tr><td>3 </td><td>13</td><td> 9</td><td>1 </td></tr>\n\t<tr><td>4 </td><td> 9</td><td> 8</td><td>2 </td></tr>\n\t<tr><td>5 </td><td> 3</td><td> 7</td><td>3 </td></tr>\n\t<tr><td>6 </td><td> 5</td><td> 6</td><td>1 </td></tr>\n\t<tr><td>7 </td><td> 6</td><td> 5</td><td>2 </td></tr>\n\t<tr><td>8 </td><td> 5</td><td> 5</td><td>3 </td></tr>\n</tbody>\n</table>\n",
   "text/latex": "\\begin{tabular}{r|llll}\n ID & read 1 & read 2 & read 3\\\\\n\\hline\n\t 1  & 13 & 12 & 1 \\\\\n\t 2  & 12 & 10 & 2 \\\\\n\t 3  & 13 &  9 & 1 \\\\\n\t 4  &  9 &  8 & 2 \\\\\n\t 5  &  3 &  7 & 3 \\\\\n\t 6  &  5 &  6 & 1 \\\\\n\t 7  &  6 &  5 & 2 \\\\\n\t 8  &  5 &  5 & 3 \\\\\n\\end{tabular}\n",
   "text/markdown": "\nID | read 1 | read 2 | read 3 | \n|---|---|---|---|---|---|---|---|\n| 1  | 13 | 12 | 1  | \n| 2  | 12 | 10 | 2  | \n| 3  | 13 |  9 | 1  | \n| 4  |  9 |  8 | 2  | \n| 5  |  3 |  7 | 3  | \n| 6  |  5 |  6 | 1  | \n| 7  |  6 |  5 | 2  | \n| 8  |  5 |  5 | 3  | \n\n\n",
   "text/plain": "  ID read 1 read 2 read 3\n1 1  13     12     1     \n2 2  12     10     2     \n3 3  13      9     1     \n4 4   9      8     2     \n5 5   3      7     3     \n6 6   5      6     1     \n7 7   6      5     2     \n8 8   5      5     3     "
  },
  "metadata": {},
  "output_type": "display_data"
 }
]
```

```{.python .input  n=57}
dataset.2<-matrix(c(1,12, 2,13, 3,3, 4,15, 5,31, 6,15, 7,4, 8,6), ncol=2, byrow=T)
dataset.2<-data.frame(dataset.2)
names(dataset.2)<-c("ID","read 4")
dataset.2

```

```{.json .output n=57}
[
 {
  "data": {
   "text/html": "<table>\n<thead><tr><th scope=col>ID</th><th scope=col>read 4</th></tr></thead>\n<tbody>\n\t<tr><td>1 </td><td>12</td></tr>\n\t<tr><td>2 </td><td>13</td></tr>\n\t<tr><td>3 </td><td> 3</td></tr>\n\t<tr><td>4 </td><td>15</td></tr>\n\t<tr><td>5 </td><td>31</td></tr>\n\t<tr><td>6 </td><td>15</td></tr>\n\t<tr><td>7 </td><td> 4</td></tr>\n\t<tr><td>8 </td><td> 6</td></tr>\n</tbody>\n</table>\n",
   "text/latex": "\\begin{tabular}{r|ll}\n ID & read 4\\\\\n\\hline\n\t 1  & 12\\\\\n\t 2  & 13\\\\\n\t 3  &  3\\\\\n\t 4  & 15\\\\\n\t 5  & 31\\\\\n\t 6  & 15\\\\\n\t 7  &  4\\\\\n\t 8  &  6\\\\\n\\end{tabular}\n",
   "text/markdown": "\nID | read 4 | \n|---|---|---|---|---|---|---|---|\n| 1  | 12 | \n| 2  | 13 | \n| 3  |  3 | \n| 4  | 15 | \n| 5  | 31 | \n| 6  | 15 | \n| 7  |  4 | \n| 8  |  6 | \n\n\n",
   "text/plain": "  ID read 4\n1 1  12    \n2 2  13    \n3 3   3    \n4 4  15    \n5 5  31    \n6 6  15    \n7 7   4    \n8 8   6    "
  },
  "metadata": {},
  "output_type": "display_data"
 }
]
```

```{.python .input  n=58}
?merge
#dataset.merged <- merge(dataset.1,dataset.2,by="ID")
```

```{.python .input  n=60}
dataset.merged <- merge(dataset.1,dataset.2,by="ID")
dataset.merged
```

```{.json .output n=60}
[
 {
  "data": {
   "text/html": "<table>\n<thead><tr><th scope=col>ID</th><th scope=col>read 1</th><th scope=col>read 2</th><th scope=col>read 3</th><th scope=col>read 4</th></tr></thead>\n<tbody>\n\t<tr><td>1 </td><td>13</td><td>12</td><td>1 </td><td>12</td></tr>\n\t<tr><td>2 </td><td>12</td><td>10</td><td>2 </td><td>13</td></tr>\n\t<tr><td>3 </td><td>13</td><td> 9</td><td>1 </td><td> 3</td></tr>\n\t<tr><td>4 </td><td> 9</td><td> 8</td><td>2 </td><td>15</td></tr>\n\t<tr><td>5 </td><td> 3</td><td> 7</td><td>3 </td><td>31</td></tr>\n\t<tr><td>6 </td><td> 5</td><td> 6</td><td>1 </td><td>15</td></tr>\n\t<tr><td>7 </td><td> 6</td><td> 5</td><td>2 </td><td> 4</td></tr>\n\t<tr><td>8 </td><td> 5</td><td> 5</td><td>3 </td><td> 6</td></tr>\n</tbody>\n</table>\n",
   "text/latex": "\\begin{tabular}{r|lllll}\n ID & read 1 & read 2 & read 3 & read 4\\\\\n\\hline\n\t 1  & 13 & 12 & 1  & 12\\\\\n\t 2  & 12 & 10 & 2  & 13\\\\\n\t 3  & 13 &  9 & 1  &  3\\\\\n\t 4  &  9 &  8 & 2  & 15\\\\\n\t 5  &  3 &  7 & 3  & 31\\\\\n\t 6  &  5 &  6 & 1  & 15\\\\\n\t 7  &  6 &  5 & 2  &  4\\\\\n\t 8  &  5 &  5 & 3  &  6\\\\\n\\end{tabular}\n",
   "text/markdown": "\nID | read 1 | read 2 | read 3 | read 4 | \n|---|---|---|---|---|---|---|---|\n| 1  | 13 | 12 | 1  | 12 | \n| 2  | 12 | 10 | 2  | 13 | \n| 3  | 13 |  9 | 1  |  3 | \n| 4  |  9 |  8 | 2  | 15 | \n| 5  |  3 |  7 | 3  | 31 | \n| 6  |  5 |  6 | 1  | 15 | \n| 7  |  6 |  5 | 2  |  4 | \n| 8  |  5 |  5 | 3  |  6 | \n\n\n",
   "text/plain": "  ID read 1 read 2 read 3 read 4\n1 1  13     12     1      12    \n2 2  12     10     2      13    \n3 3  13      9     1       3    \n4 4   9      8     2      15    \n5 5   3      7     3      31    \n6 6   5      6     1      15    \n7 7   6      5     2       4    \n8 8   5      5     3       6    "
  },
  "metadata": {},
  "output_type": "display_data"
 }
]
```

### Many to One Merging 

Now, a nice simple example of **many-to-one merging:**

```{.python .input  n=63}
install.packages("reshape",repos="http://cran.us.r-project.org", lib="C://Users//Suman//Documents//R//win-library//3.3")
library(reshape)
```

```{.json .output n=63}
[
 {
  "name": "stdout",
  "output_type": "stream",
  "text": "package 'reshape' successfully unpacked and MD5 sums checked\n\nThe downloaded binary packages are in\n\tC:\\Users\\Suman\\AppData\\Local\\Temp\\RtmpiCtZD5\\downloaded_packages\n"
 },
 {
  "name": "stderr",
  "output_type": "stream",
  "text": "Warning message:\n\"package 'reshape' was built under R version 3.3.3\""
 }
]
```

```{.python .input  n=64}
my.test.2 <- matrix(c(1, 13, 12, 1, 1, 12, 10, 2, 2, 13, 9, 1, 2, 9, 8, 2, 2, 3, 
    7, 3, 3, 5, 6, 1, 3, 6, 5, 2, 3, 5, 5, 3), ncol = 4, byrow = T)
#create sample data
```

```{.python .input  n=65}
# convert to a dataframe, a more robust format
my.test.2<-as.data.frame(my.test.2)
```

```{.python .input  n=66}
# add column names
names(my.test.2) <- c("ID","read A", "read B", "visit")
```

```{.python .input  n=67}
my.test.2
```

```{.json .output n=67}
[
 {
  "data": {
   "text/html": "<table>\n<thead><tr><th scope=col>ID</th><th scope=col>read A</th><th scope=col>read B</th><th scope=col>visit</th></tr></thead>\n<tbody>\n\t<tr><td>1 </td><td>13</td><td>12</td><td>1 </td></tr>\n\t<tr><td>1 </td><td>12</td><td>10</td><td>2 </td></tr>\n\t<tr><td>2 </td><td>13</td><td> 9</td><td>1 </td></tr>\n\t<tr><td>2 </td><td> 9</td><td> 8</td><td>2 </td></tr>\n\t<tr><td>2 </td><td> 3</td><td> 7</td><td>3 </td></tr>\n\t<tr><td>3 </td><td> 5</td><td> 6</td><td>1 </td></tr>\n\t<tr><td>3 </td><td> 6</td><td> 5</td><td>2 </td></tr>\n\t<tr><td>3 </td><td> 5</td><td> 5</td><td>3 </td></tr>\n</tbody>\n</table>\n",
   "text/latex": "\\begin{tabular}{r|llll}\n ID & read A & read B & visit\\\\\n\\hline\n\t 1  & 13 & 12 & 1 \\\\\n\t 1  & 12 & 10 & 2 \\\\\n\t 2  & 13 &  9 & 1 \\\\\n\t 2  &  9 &  8 & 2 \\\\\n\t 2  &  3 &  7 & 3 \\\\\n\t 3  &  5 &  6 & 1 \\\\\n\t 3  &  6 &  5 & 2 \\\\\n\t 3  &  5 &  5 & 3 \\\\\n\\end{tabular}\n",
   "text/markdown": "\nID | read A | read B | visit | \n|---|---|---|---|---|---|---|---|\n| 1  | 13 | 12 | 1  | \n| 1  | 12 | 10 | 2  | \n| 2  | 13 |  9 | 1  | \n| 2  |  9 |  8 | 2  | \n| 2  |  3 |  7 | 3  | \n| 3  |  5 |  6 | 1  | \n| 3  |  6 |  5 | 2  | \n| 3  |  5 |  5 | 3  | \n\n\n",
   "text/plain": "  ID read A read B visit\n1 1  13     12     1    \n2 1  12     10     2    \n3 2  13      9     1    \n4 2   9      8     2    \n5 2   3      7     3    \n6 3   5      6     1    \n7 3   6      5     2    \n8 3   5      5     3    "
  },
  "metadata": {},
  "output_type": "display_data"
 }
]
```

```{.python .input  n=69}
# above is a matrix of repeated measures on the same patient seen during multiple
# visits. The function below coerces the data frame into a 'wide' format, with
# one row per individual, renaming variables to account for missing values.
wide_mytest <- reshape(my.test.2, direction="wide",idvar="ID",timevar="visit")
wide_mytest

```

```{.json .output n=69}
[
 {
  "data": {
   "text/html": "<table>\n<thead><tr><th></th><th scope=col>ID</th><th scope=col>read A.1</th><th scope=col>read B.1</th><th scope=col>read A.2</th><th scope=col>read B.2</th><th scope=col>read A.3</th><th scope=col>read B.3</th></tr></thead>\n<tbody>\n\t<tr><th scope=row>1</th><td>1 </td><td>13</td><td>12</td><td>12</td><td>10</td><td>NA</td><td>NA</td></tr>\n\t<tr><th scope=row>3</th><td>2 </td><td>13</td><td> 9</td><td> 9</td><td> 8</td><td> 3</td><td> 7</td></tr>\n\t<tr><th scope=row>6</th><td>3 </td><td> 5</td><td> 6</td><td> 6</td><td> 5</td><td> 5</td><td> 5</td></tr>\n</tbody>\n</table>\n",
   "text/latex": "\\begin{tabular}{r|lllllll}\n  & ID & read A.1 & read B.1 & read A.2 & read B.2 & read A.3 & read B.3\\\\\n\\hline\n\t1 & 1  & 13 & 12 & 12 & 10 & NA & NA\\\\\n\t3 & 2  & 13 &  9 &  9 &  8 &  3 &  7\\\\\n\t6 & 3  &  5 &  6 &  6 &  5 &  5 &  5\\\\\n\\end{tabular}\n",
   "text/markdown": "\n| <!--/--> | ID | read A.1 | read B.1 | read A.2 | read B.2 | read A.3 | read B.3 | \n|---|---|---|\n| 1 | 1  | 13 | 12 | 12 | 10 | NA | NA | \n| 3 | 2  | 13 |  9 |  9 |  8 |  3 |  7 | \n| 6 | 3  |  5 |  6 |  6 |  5 |  5 |  5 | \n\n\n",
   "text/plain": "  ID read A.1 read B.1 read A.2 read B.2 read A.3 read B.3\n1 1  13       12       12       10       NA       NA      \n3 2  13        9        9        8        3        7      \n6 3   5        6        6        5        5        5      "
  },
  "metadata": {},
  "output_type": "display_data"
 }
]
```

```{.python .input  n=75}
ZZ<-read.table("ZZ.txt")
ZZ
```

```{.json .output n=75}
[
 {
  "data": {
   "text/html": "<table>\n<thead><tr><th scope=col>p</th><th scope=col>result</th><th scope=col>x1</th><th scope=col>x2</th></tr></thead>\n<tbody>\n\t<tr><td>0.8417549 </td><td>1         </td><td>2         </td><td> 0.4213440</td></tr>\n\t<tr><td>0.9136235 </td><td>1         </td><td>3         </td><td>-0.6412975</td></tr>\n\t<tr><td>0.8361460 </td><td>0         </td><td>2         </td><td> 0.3798271</td></tr>\n\t<tr><td>0.9850423 </td><td>1         </td><td>4         </td><td>-0.5625415</td></tr>\n\t<tr><td>0.3114491 </td><td>1         </td><td>0         </td><td> 1.4566465</td></tr>\n</tbody>\n</table>\n",
   "text/latex": "\\begin{tabular}{r|llll}\n p & result & x1 & x2\\\\\n\\hline\n\t 0.8417549  & 1          & 2          &  0.4213440\\\\\n\t 0.9136235  & 1          & 3          & -0.6412975\\\\\n\t 0.8361460  & 0          & 2          &  0.3798271\\\\\n\t 0.9850423  & 1          & 4          & -0.5625415\\\\\n\t 0.3114491  & 1          & 0          &  1.4566465\\\\\n\\end{tabular}\n",
   "text/markdown": "\np | result | x1 | x2 | \n|---|---|---|---|---|\n| 0.8417549  | 1          | 2          |  0.4213440 | \n| 0.9136235  | 1          | 3          | -0.6412975 | \n| 0.8361460  | 0          | 2          |  0.3798271 | \n| 0.9850423  | 1          | 4          | -0.5625415 | \n| 0.3114491  | 1          | 0          |  1.4566465 | \n\n\n",
   "text/plain": "  p         result x1 x2        \n1 0.8417549 1      2   0.4213440\n2 0.9136235 1      3  -0.6412975\n3 0.8361460 0      2   0.3798271\n4 0.9850423 1      4  -0.5625415\n5 0.3114491 1      0   1.4566465"
  },
  "metadata": {},
  "output_type": "display_data"
 }
]
```

```{.python .input  n=80}
ZZ[order(ZZ[,1]),]

```

```{.json .output n=80}
[
 {
  "data": {
   "text/html": "<table>\n<thead><tr><th></th><th scope=col>p</th><th scope=col>result</th><th scope=col>x1</th><th scope=col>x2</th></tr></thead>\n<tbody>\n\t<tr><th scope=row>5</th><td>0.3114491 </td><td>1         </td><td>0         </td><td> 1.4566465</td></tr>\n\t<tr><th scope=row>3</th><td>0.8361460 </td><td>0         </td><td>2         </td><td> 0.3798271</td></tr>\n\t<tr><th scope=row>1</th><td>0.8417549 </td><td>1         </td><td>2         </td><td> 0.4213440</td></tr>\n\t<tr><th scope=row>2</th><td>0.9136235 </td><td>1         </td><td>3         </td><td>-0.6412975</td></tr>\n\t<tr><th scope=row>4</th><td>0.9850423 </td><td>1         </td><td>4         </td><td>-0.5625415</td></tr>\n</tbody>\n</table>\n",
   "text/latex": "\\begin{tabular}{r|llll}\n  & p & result & x1 & x2\\\\\n\\hline\n\t5 & 0.3114491  & 1          & 0          &  1.4566465\\\\\n\t3 & 0.8361460  & 0          & 2          &  0.3798271\\\\\n\t1 & 0.8417549  & 1          & 2          &  0.4213440\\\\\n\t2 & 0.9136235  & 1          & 3          & -0.6412975\\\\\n\t4 & 0.9850423  & 1          & 4          & -0.5625415\\\\\n\\end{tabular}\n",
   "text/markdown": "\n| <!--/--> | p | result | x1 | x2 | \n|---|---|---|---|---|\n| 5 | 0.3114491  | 1          | 0          |  1.4566465 | \n| 3 | 0.8361460  | 0          | 2          |  0.3798271 | \n| 1 | 0.8417549  | 1          | 2          |  0.4213440 | \n| 2 | 0.9136235  | 1          | 3          | -0.6412975 | \n| 4 | 0.9850423  | 1          | 4          | -0.5625415 | \n\n\n",
   "text/plain": "  p         result x1 x2        \n5 0.3114491 1      0   1.4566465\n3 0.8361460 0      2   0.3798271\n1 0.8417549 1      2   0.4213440\n2 0.9136235 1      3  -0.6412975\n4 0.9850423 1      4  -0.5625415"
  },
  "metadata": {},
  "output_type": "display_data"
 }
]
```

```{.python .input  n=94}
#example 2:
# sorting examples using the mtcars dataset
attach(mtcars)
searchpaths()
```

```{.json .output n=94}
[
 {
  "name": "stderr",
  "output_type": "stream",
  "text": "The following objects are masked from mtcars (pos = 3):\n\n    am, carb, cyl, disp, drat, gear, hp, mpg, qsec, vs, wt\n\nThe following objects are masked from mtcars (pos = 4):\n\n    am, carb, cyl, disp, drat, gear, hp, mpg, qsec, vs, wt\n\nThe following objects are masked from mtcars (pos = 5):\n\n    am, carb, cyl, disp, drat, gear, hp, mpg, qsec, vs, wt\n\nThe following objects are masked from mtcars (pos = 6):\n\n    am, carb, cyl, disp, drat, gear, hp, mpg, qsec, vs, wt\n\nThe following objects are masked from mtcars (pos = 7):\n\n    am, carb, cyl, disp, drat, gear, hp, mpg, qsec, vs, wt\n\nThe following objects are masked from mtcars (pos = 8):\n\n    am, carb, cyl, disp, drat, gear, hp, mpg, qsec, vs, wt\n\nThe following objects are masked from mtcars (pos = 9):\n\n    am, carb, cyl, disp, drat, gear, hp, mpg, qsec, vs, wt\n\n"
 },
 {
  "data": {
   "text/html": "<ol class=list-inline>\n\t<li>'.GlobalEnv'</li>\n\t<li>'mtcars'</li>\n\t<li>'mtcars'</li>\n\t<li>'mtcars'</li>\n\t<li>'mtcars'</li>\n\t<li>'mtcars'</li>\n\t<li>'mtcars'</li>\n\t<li>'mtcars'</li>\n\t<li>'mtcars'</li>\n\t<li>'C:/Users/Suman/Documents/R/win-library/3.3/reshape'</li>\n\t<li>'C:/Users/Suman/Documents/R/win-library/3.3/Biobase'</li>\n\t<li>'C:/Users/Suman/Documents/R/win-library/3.3/BiocGenerics'</li>\n\t<li>'C:/Users/Suman/Anaconda3/envs/R-Env/R/library/parallel'</li>\n\t<li>'C:/Users/Suman/Documents/R/win-library/3.3/formatR'</li>\n\t<li>'jupyter:irkernel'</li>\n\t<li>'C:/Users/Suman/Anaconda3/envs/R-Env/R/library/stats'</li>\n\t<li>'C:/Users/Suman/Anaconda3/envs/R-Env/R/library/graphics'</li>\n\t<li>'C:/Users/Suman/Anaconda3/envs/R-Env/R/library/grDevices'</li>\n\t<li>'C:/Users/Suman/Anaconda3/envs/R-Env/R/library/utils'</li>\n\t<li>'C:/Users/Suman/Anaconda3/envs/R-Env/R/library/datasets'</li>\n\t<li>'C:/Users/Suman/Anaconda3/envs/R-Env/R/library/methods'</li>\n\t<li>'Autoloads'</li>\n\t<li>'C:/Users/Suman/Anaconda3/envs/R-Env/R/library/base'</li>\n</ol>\n",
   "text/latex": "\\begin{enumerate*}\n\\item '.GlobalEnv'\n\\item 'mtcars'\n\\item 'mtcars'\n\\item 'mtcars'\n\\item 'mtcars'\n\\item 'mtcars'\n\\item 'mtcars'\n\\item 'mtcars'\n\\item 'mtcars'\n\\item 'C:/Users/Suman/Documents/R/win-library/3.3/reshape'\n\\item 'C:/Users/Suman/Documents/R/win-library/3.3/Biobase'\n\\item 'C:/Users/Suman/Documents/R/win-library/3.3/BiocGenerics'\n\\item 'C:/Users/Suman/Anaconda3/envs/R-Env/R/library/parallel'\n\\item 'C:/Users/Suman/Documents/R/win-library/3.3/formatR'\n\\item 'jupyter:irkernel'\n\\item 'C:/Users/Suman/Anaconda3/envs/R-Env/R/library/stats'\n\\item 'C:/Users/Suman/Anaconda3/envs/R-Env/R/library/graphics'\n\\item 'C:/Users/Suman/Anaconda3/envs/R-Env/R/library/grDevices'\n\\item 'C:/Users/Suman/Anaconda3/envs/R-Env/R/library/utils'\n\\item 'C:/Users/Suman/Anaconda3/envs/R-Env/R/library/datasets'\n\\item 'C:/Users/Suman/Anaconda3/envs/R-Env/R/library/methods'\n\\item 'Autoloads'\n\\item 'C:/Users/Suman/Anaconda3/envs/R-Env/R/library/base'\n\\end{enumerate*}\n",
   "text/markdown": "1. '.GlobalEnv'\n2. 'mtcars'\n3. 'mtcars'\n4. 'mtcars'\n5. 'mtcars'\n6. 'mtcars'\n7. 'mtcars'\n8. 'mtcars'\n9. 'mtcars'\n10. 'C:/Users/Suman/Documents/R/win-library/3.3/reshape'\n11. 'C:/Users/Suman/Documents/R/win-library/3.3/Biobase'\n12. 'C:/Users/Suman/Documents/R/win-library/3.3/BiocGenerics'\n13. 'C:/Users/Suman/Anaconda3/envs/R-Env/R/library/parallel'\n14. 'C:/Users/Suman/Documents/R/win-library/3.3/formatR'\n15. 'jupyter:irkernel'\n16. 'C:/Users/Suman/Anaconda3/envs/R-Env/R/library/stats'\n17. 'C:/Users/Suman/Anaconda3/envs/R-Env/R/library/graphics'\n18. 'C:/Users/Suman/Anaconda3/envs/R-Env/R/library/grDevices'\n19. 'C:/Users/Suman/Anaconda3/envs/R-Env/R/library/utils'\n20. 'C:/Users/Suman/Anaconda3/envs/R-Env/R/library/datasets'\n21. 'C:/Users/Suman/Anaconda3/envs/R-Env/R/library/methods'\n22. 'Autoloads'\n23. 'C:/Users/Suman/Anaconda3/envs/R-Env/R/library/base'\n\n\n",
   "text/plain": " [1] \".GlobalEnv\"                                             \n [2] \"mtcars\"                                                 \n [3] \"mtcars\"                                                 \n [4] \"mtcars\"                                                 \n [5] \"mtcars\"                                                 \n [6] \"mtcars\"                                                 \n [7] \"mtcars\"                                                 \n [8] \"mtcars\"                                                 \n [9] \"mtcars\"                                                 \n[10] \"C:/Users/Suman/Documents/R/win-library/3.3/reshape\"     \n[11] \"C:/Users/Suman/Documents/R/win-library/3.3/Biobase\"     \n[12] \"C:/Users/Suman/Documents/R/win-library/3.3/BiocGenerics\"\n[13] \"C:/Users/Suman/Anaconda3/envs/R-Env/R/library/parallel\" \n[14] \"C:/Users/Suman/Documents/R/win-library/3.3/formatR\"     \n[15] \"jupyter:irkernel\"                                       \n[16] \"C:/Users/Suman/Anaconda3/envs/R-Env/R/library/stats\"    \n[17] \"C:/Users/Suman/Anaconda3/envs/R-Env/R/library/graphics\" \n[18] \"C:/Users/Suman/Anaconda3/envs/R-Env/R/library/grDevices\"\n[19] \"C:/Users/Suman/Anaconda3/envs/R-Env/R/library/utils\"    \n[20] \"C:/Users/Suman/Anaconda3/envs/R-Env/R/library/datasets\" \n[21] \"C:/Users/Suman/Anaconda3/envs/R-Env/R/library/methods\"  \n[22] \"Autoloads\"                                              \n[23] \"C:/Users/Suman/Anaconda3/envs/R-Env/R/library/base\"     "
  },
  "metadata": {},
  "output_type": "display_data"
 }
]
```

```{.python .input  n=91}

```

```{.json .output n=91}
[
 {
  "data": {
   "text/html": "32",
   "text/latex": "32",
   "text/markdown": "32",
   "text/plain": "[1] 32"
  },
  "metadata": {},
  "output_type": "display_data"
 }
]
```
