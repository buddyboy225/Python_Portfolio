# Python_Portfolio_Thompson
This is the Portfolio of Python Code I learned during BISC-450C

## Python Fundamentals
This was an inital introduction on how python coding really worked.
```python
#Any python interpreter can be used as a calculator
4*2+12
```




    20




```python
# Lets save a value to a variable
weight_kg= 69
```


```python
print(weight_kg)
```

    69



```python
#Weight0= valid
#0Weight= invalid
#weight and Weight are different

```


```python
# Types of Data
# There are three common types of data
# Interger Numbers
# Floating Point numbers
# strings

```


```python
#floating
weight_kg = 60.3

```


```python
 #string
patient_id = '001'
```


```python
#use varibale in python
weight_lb = 25 * weight_kg
print(weight_lb)
```

    1507.5



```python
#add prefix to patient ID
patient_id = 'inflam_' + patient_id
print(patient_id)
```

    inflam_001



```python
# combining print statements
print(patient_id, 'weight in kilograms:',weight_kg)
```

    inflam_001 weight in kilograms: 60.3



```python
# function inception

print(type(60.3))
print(type(patient_id))
```

    <class 'float'>
    <class 'str'>



```python
# calculations inside print function
print('weight in kg', 4.2 * weight_kg )
```

    weight in kg 253.26



```python
weight_kg = 32
print('weight in kilograms is now:', weight_kg)
```

    weight in kilograms is now: 32



```python

```



## Analyzing Patient Data

In this analysis we looked at inflammation data for multiple patients.

```python
import numpy
```


```python
numpy .loadtxt(fname = 'inflammation-01.csv', delimiter = ',')
```




    array([[0., 0., 1., ..., 3., 0., 0.],
           [0., 1., 2., ..., 1., 0., 1.],
           [0., 1., 1., ..., 2., 1., 1.],
           ...,
           [0., 1., 1., ..., 1., 1., 1.],
           [0., 0., 0., ..., 0., 2., 0.],
           [0., 0., 1., ..., 1., 1., 0.]])




```python
data = numpy.loadtxt(fname = 'inflammation-01.csv', delimiter = ',')
```


```python
print(data)
```

    [[0. 0. 1. ... 3. 0. 0.]
     [0. 1. 2. ... 1. 0. 1.]
     [0. 1. 1. ... 2. 1. 1.]
     ...
     [0. 1. 1. ... 1. 1. 1.]
     [0. 0. 0. ... 0. 2. 0.]
     [0. 0. 1. ... 1. 1. 0.]]



```python
print(type(data))
```

    <class 'numpy.ndarray'>



```python
print(data.shape)
```

    (60, 40)



```python
print('first value in data', data[0,0])
```

    first value in data 0.0



```python
print('middle value in data', data[30,20])
```

    middle value in data 13.0



```python
print(data[0:4,0:10])
```

    [[0. 0. 1. 3. 1. 2. 4. 7. 8. 3.]
     [0. 1. 2. 1. 2. 1. 3. 2. 2. 6.]
     [0. 1. 1. 3. 3. 2. 6. 2. 5. 9.]
     [0. 0. 2. 0. 4. 2. 2. 1. 6. 7.]]



```python
small = data [:3, 36:]
```


```python
print ('small is:')
```

    small is:



```python
print(small)
```

    [[2. 3. 0. 0.]
     [1. 1. 0. 1.]
     [2. 2. 1. 1.]]



```python
#use numpy function
print(numpy.mean(data))
```

    6.14875



```python
maxval, minval, stdval = numpy.amax(data), numpy.amin(data), numpy.std(data)

```


```python
maxval = numpy.amax(data)
minval = numpy.amin(data)
stdval = numpy.std(data)
```


```python
print(maxval)
print(minval)
print(stdval)
```

    20.0
    0.0
    4.613833197118566



```python
print('maximum inflammation:',maxval)
print('maximum inflammation:',minval)
print('maximum inflammation:',stdval)
```

    maximum inflammation: 20.0
    maximum inflammation: 0.0
    maximum inflammation: 4.613833197118566



```python
patient_0 = data[0,:]
print('maximum inflammation for patient 0:', numpy.amax(patient_0))
```

    maximum inflammation for patient 0: 18.0



```python
print('maximum inflammation for patient 0:', numpy.amax(data[2, :]))
```

    maximum inflammation for patient 0: 19.0



```python
print(numpy.mean(data, axis=0))
```

    [ 0.          0.45        1.11666667  1.75        2.43333333  3.15
      3.8         3.88333333  5.23333333  5.51666667  5.95        5.9
      8.35        7.73333333  8.36666667  9.5         9.58333333 10.63333333
     11.56666667 12.35       13.25       11.96666667 11.03333333 10.16666667
     10.          8.66666667  9.15        7.25        7.33333333  6.58333333
      6.06666667  5.95        5.11666667  3.6         3.3         3.56666667
      2.48333333  1.5         1.13333333  0.56666667]



```python
print(numpy.mean(data, axis=0).shape)
```

    (40,)



```python
print(numpy.mean(data, axis=1))
```

    [5.45  5.425 6.1   5.9   5.55  6.225 5.975 6.65  6.625 6.525 6.775 5.8
     6.225 5.75  5.225 6.3   6.55  5.7   5.85  6.55  5.775 5.825 6.175 6.1
     5.8   6.425 6.05  6.025 6.175 6.55  6.175 6.35  6.725 6.125 7.075 5.725
     5.925 6.15  6.075 5.75  5.975 5.725 6.3   5.9   6.75  5.925 7.225 6.15
     5.95  6.275 5.7   6.1   6.825 5.975 6.725 5.7   6.25  6.4   7.05  5.9  ]


## Storing Values in Lists
This section showed us how to store values in lists so that it can be used later.

```python
odds=[1,3,5,7]
print('odds are:', odds)
```

    odds are: [1, 3, 5, 7]



```python
print('first element;', odds[0])
print('last element;', odds[3])
print('"-1" element;', odds[-1])
```

    first element; 1
    last element; 7
    "-1" element; 7



```python
#typo in darwins name
names = ['curie', 'darwing','turing']
print('names is originally:', names)
names[1] = 'darwin' #corrected name
print('final value of names:',names)
```

    names is originally: ['curie', 'darwing', 'turing']
    final value of names: ['curie', 'darwin', 'turing']



```python
name = 'Darwin'

```


```python
odds.append(11)
print('odds after adding a value:', odds)
```

    odds after adding a value: [1, 3, 5, 7, 11]



```python
removed_element= odds.pop(0) 
print('odds after removing the first element:', odds)
print('Removed_element:', removed_element)
```

    odds after removing the first element: [3, 5, 7, 11]
    Removed_element: 1



```python
odds.reverse()
print('Odds after Reversing:',odds)
```

    Odds after Reversing: [11, 7, 5, 3]



```python
odds=[3,5,7]
primes=odds
primes.append(2)
print ('Primes:',primes)
print('odds:',odds)
```

    Primes: [3, 5, 7, 2]
    odds: [3, 5, 7, 2]



```python
odds=[3,5,7]
primes= list(odds)
primes.append(2)
print('primes:',primes)
print('odds:', odds)
```

    primes: [3, 5, 7, 2]
    odds: [3, 5, 7]



```python
binomial_name="Drosophila Melanogaster"
group= binomial_name[0:10]
print('group:',group)

species= binomial_name[11:23]
print('Species:',species)
chromosomes= ['X','Y','2','3','4']
autosomes= chromosomes[2:5]
print('autosomes:',autosomes)

last=chromosomes[-1]
print('last:',last)
```

    group: Drosophila
    Species: Melanogaster
    autosomes: ['2', '3', '4']
    last: 4



```python
 date= 'Tuesday November 5, 2024'
day= date[0:7]
print('Using 0 to begin range today:',day)
day=date[:7]
print('omitting beginning index:',day)

```

    Using 0 to begin range today: Tuesday
    omitting beginning index: Tuesday



```python
months=['january','february','march','april','may','june','july','august','september','october','november','december']
sond= months[8:12]
print('With known last position:',sond)

sond=months[8:len(months)]
print('Using length to get last entry;',sond)
sond=months[8:]
print("Omitting ending index:",sond)
```

    With known last position: ['september', 'october', 'november', 'december']
    Using length to get last entry; ['september', 'october', 'november', 'december']
    Omitting ending index: ['september', 'october', 'november', 'december']



```python
 
```
## Using Loops

This section showed us how loops work in python coding.

```python
odds= [1,3,5,7]

```


```python
print(odds[0])
print(odds[1])
print(odds[2])
print(odds[3])
 

```

    1
    3
    5
    7



```python
odds= [1,3,5]
print(odds[0])
print(odds[1])
print(odds[2])
print(odds[3])
```

    1
    3
    5



    ---------------------------------------------------------------------------

    IndexError                                Traceback (most recent call last)

    <ipython-input-3-192edaab5a56> in <module>
          3 print(odds[1])
          4 print(odds[2])
    ----> 5 print(odds[3])
    

    IndexError: list index out of range



```python
odds= [1,3,5,7]

for num in odds:
    print(num)
     
```

    1
    3
    5
    7



```python
odds= [1,3,5,7,9,12,13,69,420]

for num in odds:
    print(num)
```

    1
    3
    5
    7
    9
    12
    13
    69
    420



```python
length=0
names=['curie','darwin','turing']
for value in names:
    length = length + 1
print('there are',length,'names in the list.')
```

    there are 3 names in the list.



```python
name="Rosalind"
for name in ['curie','darwin','turing']:
    print(name)
print('after the loop,name is:',name)
```

    curie
    darwin
    turing
    after the loop,name is: turing



```python
print(len([0,1,2,3]))
```

    4



```python
name= ['curie','darwin','turing']

print(len(name))
```

    3



```python

```

## Using Multiple Files

This section is an example of code where multiple files were accessed.

```python
import glob
```


```python
print(glob.glob('inflammation*.csv'))
```

    ['inflammation-10.csv', 'inflammation-09.csv', 'inflammation-11.csv', 'inflammation-06.csv', 'inflammation-05.csv', 'inflammation-08.csv', 'inflammation-01.csv', 'inflammation-07.csv', 'inflammation-04.csv', 'inflammation-03.csv', 'inflammation-02.csv', 'inflammation-12.csv']



```python
import glob
import numpy
import matplotlib.pyplot

filenames= sorted(glob.glob('inflammation*.csv'))
filenames=filenames[0:3]

for filenames in filenames:
    print(filenames)
    
    data= numpy.loadtxt(fname= filenames, delimiter=',')

    fig= matplotlib.pyplot.figure(figsize = (10.0, 3.0))

    axes1=fig.add_subplot(1,3,1)
    axes2=fig.add_subplot(1,3,2)
    axes3=fig.add_subplot(1,3,3)

    axes1.set_ylabel('average')
    axes1.plot(numpy.mean( data,axis=0))

    axes2.set_ylabel('max')
    axes2.plot(numpy.amax( data,axis=0))

    axes3.set_ylabel('min')
    axes3.plot(numpy.amin( data,axis=0))

    fig.tight_layout()
    matplotlib.pyplot.show()

```

    inflammation-01.csv



![png](output_2_1.png)


    inflammation-02.csv



![png](output_2_3.png)


    inflammation-03.csv



![png](output_2_5.png)



```python

```
