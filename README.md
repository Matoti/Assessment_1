echo "# Assessment_1" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/Matoti/Assessment_1.git
git push -u origin main
# main.py

from mean_var_std import calculate
import unittest

class TestMeanVarStd(unittest.TestCase):
    
    def test_calculate(self):
        self.assertEqual(calculate([0,1,2,3,4,5,6,7,8]), {
            'mean': [[3.0, 4.0, 5.0], [1.0, 4.0, 7.0], 4.0],
            'variance': [[6.0, 6.0, 6.0], [0.6666666666666666, 0.6666666666666666, 0.6666666666666666], 6.666666666666667],
            'standard deviation': [[2.449489742783178, 2.449489742783178, 2.449489742783178], [0.816496580927726, 0.816496580927726, 0.816496580927726], 2.581988897471611],
            'max': [[6, 7, 8], [2, 5, 8], 8],
            'min': [[0, 1, 2], [0, 3, 6], 0],
            'sum': [[9, 12, 15], [3, 12, 21], 36]
        })
        
        with self.assertRaises(ValueError):
            calculate([1,2,3,4,5,6,7,8])  # This should raise a ValueError because the list doesn't have 9 elements

if __name__ == '__main__':
    unittest.main()
