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

## Making Choices

This section is an example of using python code to see how data can give different responses.

```python
num=37
if num > 100:
    print ('greater:')
else:
    print('not greater:')
print('done meow')

```

    not greater:
    done meow



```python
num=53
print('before conditional...')
if num > 100:
    print(num, 'is greater than 100')
    
    
print('...after conditional')
```

    before conditional...
    ...after conditional



```python
num=-3

if num > 0:
    print(num, 'is positive ')
elif num == 0:
    print(num, 'is zero')
else:
    print(num,'is negative innit')
```

    -3 is negative innit



```python
if (1>0) and (-1 >= 0):
    print('both parts are true')
else:
    print('at least one part is false')
```

    at least one part is false



```python
if (1>0) or (-1 >= 0):
    print('at least one am are true')
else:
    print('both em is false')
```

    at least one am are true



```python
import numpy
```


```python

```

```python
import numpy
```


```python
data=numpy.loadtxt(fname='inflammation-01.csv', delimiter=',')
```


```python
max_inflammation_0 = numpy.amax(data, axis = 0)[0]
```


```python
max_inflammation_20 = numpy.amax(data, axis = 0)[20]

if max_inflammation_0 == 0 and max_inflammation_20 ==0:
    print('Suspicious looking maxima!')

elif numpy.sum(numpy.amin(data,axis=0))==0:
    print('minima add up to zero!' )
    
else:
    print('seems ok to me innit')
```

    seems ok to me innit



```python
data=numpy.loadtxt(fname='inflammation-03.csv', delimiter=',')

max_inflammation_0 = numpy.amax(data, axis = 0)[0]

max_inflammation_20 = numpy.amax(data, axis = 0)[20]

if max_inflammation_0 ==0 and max_inflammation_20 ==20:
    print('suspicious looking maxiuma innit')
    
elif numpy.sum(numpy.amin(data,axis=0))==0:
    print('maxima add up to zero!-> m8 you are healthy' )
    
else:
    print('seems ok if you asked me')
```

    maxima add up to zero!-> m8 you are healthy



```python

```

## Functions

This section shows us the way that functions can affect inputs to outputs.

```python
fahrenheit_val=69
celsius_val= ((fahrenheit_val-32)*(5/9))

print(celsius_val)
```

    20.555555555555557



```python
fahrenheit_val2=43
celsius_val2= ((fahrenheit_val2-32)*(5/9))
print(celsius_val2)
```

    6.111111111111112



```python
def explicit_fahr_to_celsius(temp):
    converted= ((temp-32)*5/9)
    return converted

```


```python
def fahr_to_celsuis(temp):
    return ((temp-32)*5/9)
```


```python
fahr_to_celsuis(32)
```




    0.0




```python
explicit_fahr_to_celsius(23)
```




    -5.0




```python
 print('freezing point of water:', fahr_to_celsuis(32),'C')
 print('boiling point of water:', fahr_to_celsuis(212),'C')
```

    freezing point of water: 0.0 C
    boiling point of water: 100.0 C



```python
def celsuis_to_kelvin(temp_c):
    return temp_c + 273.15

print('Freezing point of water in Kelvin',celsuis_to_kelvin(0))
```

    Freezing point of water in Kelvin 273.15



```python
def fahr_to_kelvin(temp_f):
    temp_c = fahr_to_celsuis (temp_f)
    temp_k=celsuis_to_kelvin (temp_c)
    return temp_k 

print('freezing point of water in kelvin', fahr_to_kelvin(212.0))
    
```

    freezing point of water in kelvin 373.15



```python
print('again temp in kelvin was:', temp_k)
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-14-5f2ca5bc1217> in <module>
    ----> 1 print('again temp in kelvin was:', temp_k)
    

    NameError: name 'temp_k' is not defined



```python
temp_kelvint= fahr_to_kelvin(212.0)
print('Temp in Kelvin was',temp_kelvint)
```

    Temp in Kelvin was 373.15



```python
temp_kelvint
```




    373.15




```python
def print_temperatures():
    print('Temp in Fahrenheit was:',temp_fahr)
    print('temp in kelvin was:',temp_kelvin)
    
temp_fahr=212.0
temp_kelvin= fahr_to_kelvin(temp_fahr)

print_temperatures()
```

    Temp in Fahrenheit was: 212.0
    temp in kelvin was: 373.15



```python
 
```
```python
import numpy
import glob
import matplotlib.pyplot
import matplotlib
```


```python

def visualize (filename):
    
    data = numpy. loadtxt(fname = filename, delimiter = ',')
    
    fig = matplotlib.pyplot.figure(figsize=(10.0, 3.0))
    
    axes1 = fig.add_subplot(1, 3, 1)
    axes2 = fig.add_subplot(1, 3, 2)
    axes3 = fig.add_subplot(1, 3, 3)
    
    axes1.set_ylabel( 'average')
    axes1.plot(numpy.mean(data, axis=0))
    
    axes2.set_ylabel( 'max')
    axes2.plot(numpy.amax(data, axis=0))
    
    axes3.set_ylabel( 'min')
    axes3.plot(numpy.amin(data, axis=0))
    
    fig. tight_layout ()
    matplotlib.pyplot.show()
```


```python
def detect_problems (filename) :
    
    data = numpy.loadtxt(fname = filename, delimiter = ',')
    
    if numpy.amax(data, axis = 0)[0] == 0 and numpy.amax(data, axis=0)[20] == 20:
        print ("Suspicious looking maxima!")
    elif numpy.sum(numpy.amin(data, axis=0)) == 0:
        print( 'Minima add up to zero!')
    else:
        print( 'Seems ok!')
```


```python
filenames = sorted(glob.glob('inflammation*.csv'))

for filename in filenames:
    print (filename)
    visualize (filename)
    detect_problems (filename)
```

    inflammation-01.csv



![png](output_3_1.png)


    Suspicious looking maxima!
    inflammation-02.csv



![png](output_3_3.png)


    Suspicious looking maxima!
    inflammation-03.csv



![png](output_3_5.png)


    Minima add up to zero!
    inflammation-04.csv



![png](output_3_7.png)


    Suspicious looking maxima!
    inflammation-05.csv



![png](output_3_9.png)


    Suspicious looking maxima!
    inflammation-06.csv



![png](output_3_11.png)


    Suspicious looking maxima!
    inflammation-07.csv



![png](output_3_13.png)


    Suspicious looking maxima!
    inflammation-08.csv



![png](output_3_15.png)


    Minima add up to zero!
    inflammation-09.csv



![png](output_3_17.png)


    Suspicious looking maxima!
    inflammation-10.csv



![png](output_3_19.png)


    Suspicious looking maxima!
    inflammation-11.csv



![png](output_3_21.png)


    Minima add up to zero!
    inflammation-12.csv



![png](output_3_23.png)


    Suspicious looking maxima!



```python
def offset_mean(data, target_mean_value) :
    return (data - numpy.mean (data)) + target_mean_value
```


```python
z = numpy.zeros ((2,2))
print(offset_mean (z, 3))
```

    [[3. 3.]
     [3. 3.]]



```python
data = numpy. loadtxt(fname = 'inflammation-01.csv', delimiter = ',')

print(offset_mean(data,0))
```

    [[-6.14875 -6.14875 -5.14875 ... -3.14875 -6.14875 -6.14875]
     [-6.14875 -5.14875 -4.14875 ... -5.14875 -6.14875 -5.14875]
     [-6.14875 -5.14875 -5.14875 ... -4.14875 -5.14875 -5.14875]
     ...
     [-6.14875 -5.14875 -5.14875 ... -5.14875 -5.14875 -5.14875]
     [-6.14875 -6.14875 -6.14875 ... -6.14875 -4.14875 -6.14875]
     [-6.14875 -6.14875 -5.14875 ... -5.14875 -5.14875 -6.14875]]



```python
print('original min, mean and max are:', numpy.amin(data), numpy.mean(data), numpy.amax(data))
offset_data = offset_mean (data,0)
print('min, mean, and max of offset data are:',
    numpy.amin(offset_data), 
    numpy.mean (offset_data),
    numpy.amax(offset_data))
```

    original min, mean and max are: 0.0 6.14875 20.0
    min, mean, and max of offset data are: -6.14875 2.842170943040401e-16 13.85125



```python
 print('std dev before and after:', numpy.std(data), numpy.std(offset_data))
```

    std dev before and after: 4.613833197118566 4.613833197118566



```python
print( 'difference in standard deviation before and after:',
    numpy. std (data) - numpy.std(offset_data))
```

    difference in standard deviation before and after: 0.0



```python
def offset_mean(data, target_mean_value) :
    return (data - numpy-mean (data)) + target_mean_value
```


```python
def offset_mean(data, target_mean_value) :
    """Return a new array continaing the original data with its mean offset to match the desired value"""
    return (data - numpy.mean (data)) + target_mean_value
```


```python
help(offset_mean)
```

    Help on function offset_mean in module __main__:
    
    offset_mean(data, target_mean_value)
        Return a new array continaing the original data with its mean offset to match the desired value
    



```python
def offset_mean(data, target_mean_value) : 
    """Return a new array containing the original data
    with its mean offset to match the desired value.
    
    Examples
    --------
    
    >>> Offset_mean([1,2,3], 0)
    array ([-1., 0., 1.])
    """
    return (data - numpy.mean (data)) + target_mean_value
```


```python
help(offset_mean)
```

    Help on function offset_mean in module __main__:
    
    offset_mean(data, target_mean_value)
        Return a new array containing the original data
        with its mean offset to match the desired value.
        
        Examples
        --------
        
        >>> Offset_mean([1,2,3], 0)
        array ([-1., 0., 1.])
    



```python
numpy.loadtxt('inflammation-01.csv', delimiter = ',')
```




    array([[0., 0., 1., ..., 3., 0., 0.],
           [0., 1., 2., ..., 1., 0., 1.],
           [0., 1., 1., ..., 2., 1., 1.],
           ...,
           [0., 1., 1., ..., 1., 1., 1.],
           [0., 0., 0., ..., 0., 2., 0.],
           [0., 0., 1., ..., 1., 1., 0.]])




```python
def offset_mean(data, target_mean_value=0.0) : 
    """Return a new array containing the original data
    with its mean offset to match the desired value.
    
    Examples
    --------
    
    >>> Offset_mean([1,2,3], 0)
    array ([-1., 0., 1.])
    """
    return (data - numpy.mean (data)) + target_mean_value
```


```python
test_data = numpy.zeros ( (2,2))
print(offset_mean (test_data, 3))
```

    [[3. 3.]
     [3. 3.]]



```python
 print(offset_mean (test_data))
```

    [[0. 0.]
     [0. 0.]]



```python
def display(a=1, b=2, c=3) :
    print('A:',a , 'B:',b, 'C:',c)
print('no parameters: ')
display()
print('one parameter: ')
display (55)
print( 'two parameters:')
display (55,66)
```

    no parameters: 
    A: 1 B: 2 C: 3
    one parameter: 
    A: 55 B: 2 C: 3
    two parameters:
    A: 55 B: 66 C: 3



```python
print('only setting the value of c')
display(c=77)
```

    only setting the value of c
    A: 1 B: 2 C: 77



```python
help (numpy.loadtxt)

```

    Help on function loadtxt in module numpy:
    
    loadtxt(fname, dtype=<class 'float'>, comments='#', delimiter=None, converters=None, skiprows=0, usecols=None, unpack=False, ndmin=0, encoding='bytes', max_rows=None)
        Load data from a text file.
        
        Each row in the text file must have the same number of values.
        
        Parameters
        ----------
        fname : file, str, or pathlib.Path
            File, filename, or generator to read.  If the filename extension is
            ``.gz`` or ``.bz2``, the file is first decompressed. Note that
            generators should return byte strings for Python 3k.
        dtype : data-type, optional
            Data-type of the resulting array; default: float.  If this is a
            structured data-type, the resulting array will be 1-dimensional, and
            each row will be interpreted as an element of the array.  In this
            case, the number of columns used must match the number of fields in
            the data-type.
        comments : str or sequence of str, optional
            The characters or list of characters used to indicate the start of a
            comment. None implies no comments. For backwards compatibility, byte
            strings will be decoded as 'latin1'. The default is '#'.
        delimiter : str, optional
            The string used to separate values. For backwards compatibility, byte
            strings will be decoded as 'latin1'. The default is whitespace.
        converters : dict, optional
            A dictionary mapping column number to a function that will parse the
            column string into the desired value.  E.g., if column 0 is a date
            string: ``converters = {0: datestr2num}``.  Converters can also be
            used to provide a default value for missing data (but see also
            `genfromtxt`): ``converters = {3: lambda s: float(s.strip() or 0)}``.
            Default: None.
        skiprows : int, optional
            Skip the first `skiprows` lines, including comments; default: 0.
        usecols : int or sequence, optional
            Which columns to read, with 0 being the first. For example,
            ``usecols = (1,4,5)`` will extract the 2nd, 5th and 6th columns.
            The default, None, results in all columns being read.
        
            .. versionchanged:: 1.11.0
                When a single column has to be read it is possible to use
                an integer instead of a tuple. E.g ``usecols = 3`` reads the
                fourth column the same way as ``usecols = (3,)`` would.
        unpack : bool, optional
            If True, the returned array is transposed, so that arguments may be
            unpacked using ``x, y, z = loadtxt(...)``.  When used with a structured
            data-type, arrays are returned for each field.  Default is False.
        ndmin : int, optional
            The returned array will have at least `ndmin` dimensions.
            Otherwise mono-dimensional axes will be squeezed.
            Legal values: 0 (default), 1 or 2.
        
            .. versionadded:: 1.6.0
        encoding : str, optional
            Encoding used to decode the inputfile. Does not apply to input streams.
            The special value 'bytes' enables backward compatibility workarounds
            that ensures you receive byte arrays as results if possible and passes
            'latin1' encoded strings to converters. Override this value to receive
            unicode arrays and pass strings as input to converters.  If set to None
            the system default is used. The default value is 'bytes'.
        
            .. versionadded:: 1.14.0
        max_rows : int, optional
            Read `max_rows` lines of content after `skiprows` lines. The default
            is to read all the lines.
        
            .. versionadded:: 1.16.0
        
        Returns
        -------
        out : ndarray
            Data read from the text file.
        
        See Also
        --------
        load, fromstring, fromregex
        genfromtxt : Load data with missing values handled as specified.
        scipy.io.loadmat : reads MATLAB data files
        
        Notes
        -----
        This function aims to be a fast reader for simply formatted files.  The
        `genfromtxt` function provides more sophisticated handling of, e.g.,
        lines with missing values.
        
        .. versionadded:: 1.10.0
        
        The strings produced by the Python float.hex method can be used as
        input for floats.
        
        Examples
        --------
        >>> from io import StringIO   # StringIO behaves like a file object
        >>> c = StringIO(u"0 1\n2 3")
        >>> np.loadtxt(c)
        array([[0., 1.],
               [2., 3.]])
        
        >>> d = StringIO(u"M 21 72\nF 35 58")
        >>> np.loadtxt(d, dtype={'names': ('gender', 'age', 'weight'),
        ...                      'formats': ('S1', 'i4', 'f4')})
        array([(b'M', 21, 72.), (b'F', 35, 58.)],
              dtype=[('gender', 'S1'), ('age', '<i4'), ('weight', '<f4')])
        
        >>> c = StringIO(u"1,0,2\n3,0,4")
        >>> x, y = np.loadtxt(c, delimiter=',', usecols=(0, 2), unpack=True)
        >>> x
        array([1., 3.])
        >>> y
        array([2., 4.])
    



```python
numpy.loadtxt('inflammation-01.csv',delimiter=',')
```




    array([[0., 0., 1., ..., 3., 0., 0.],
           [0., 1., 2., ..., 1., 0., 1.],
           [0., 1., 1., ..., 2., 1., 1.],
           ...,
           [0., 1., 1., ..., 1., 1., 1.],
           [0., 0., 0., ..., 0., 2., 0.],
           [0., 0., 1., ..., 1., 1., 0.]])




```python
def s(p):
    a = 0
    for v in p:
        a += v
    m = a / len(p)
    d = 0
    for v in p:
        d += (v - m) * (v - m)
    return numpy.sqrt(d / (len(p) - 1))

def std_dev(sample) :
    sample_sum = 0
    for value in sample:
        sample_sum += value
    
    sample_mean = sample_sum / len (sample)

    sum_squared_devs = 0

    for value in sample:
        sum_squared_devs += (value - sample_mean) * (value - sample_mean)

    return numpy.sqrt(sum_squared_devs / (len(sample) - 1))
```


```python

```
