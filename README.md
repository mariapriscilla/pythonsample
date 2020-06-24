# pythonsample
python assignment
def correlCo(someList1, someList2):

    # First establish the means and standard deviations for both lists.
    xMean = mean(someList1)
    yMean = mean(someList2)
    xStandDev = standDev(someList1)
    yStandDev = standDev(someList2)
    zList1 = []
    zList2 = []

    # Create 2 new lists taking (a[i]-a's Mean)/standard deviation of a
    for x in someList1:
        z1 = ((float(x)-xMean)/xStandDev)
        zList1.append(z1)

    for y in someList2:
        z2 = ((float(y)-yMean)/yStandDev)
        zList2.append(z2)

    # Mapping out the lists to be float values instead of string     
    zList1 = list(map(float,zList1))
    zList2 = list(map(float,zList2))
    # Multiplying each value from the lists
    zFinal = [a*b for a,b in zip(zList1,zList2)]
    totalZ = 0
    # Taking the sum of all the products
    for a in zFinal:
        totalZ += a
    # Finally calculating correlation coefficient
    r = (1/(len(someList1) - 1)) * totalZ

    return r
