# test3
# Lab 4 -> Step 1 -> Test 3
from unit_testing import check_equal
from T082_M1_load_data import load_data


def test_thing() -> None:
    """
    tests the thing
    """
    #fails = student_failures_dictionary("student-mat.csv")
    #health = student_health_dictionary("student-mat.csv")
    #schools = student_school_dictionary("student-mat.csv")
    #age = student_age_dictionary("student-mat.csv")

    # print(check_equal(fails.keys(), ({1: 1, 2: 2, 3: 3, 4: 4, 5: 5, 6: 6, 7: 7,
    #                                8: 8, 9: 9, 10: 10}).keys()))
    # print(check_equal(health.keys(), ({1: 1, 2: 2, 3: 3, 4: 4, 5: 5}).keys()))
    # print(check_equal(schools.keys(), ({"GP": 1, "MB": 2, "CF": 3, "BD": 4,
    #                                    "MS": 5}).keys()))
    # print(check_equal(age.keys(), ({15: 1, 16: 2, 17: 3, 18: 4, 19: 5, 20: 6,
    #                                21: 7, 22: 8}).keys()))

    tests_passed = 0
    tests_failed = 0
    tests_completed = 0

    passed = check_equal(set(T082_M1_load_data("student-mat.csv",
                                               "failures").get("GP")[0].keys()),
                         {"School", "Age", "StudyTime", "Health",
                          'Absences', 'G1', 'G2', 'G3'})

    if passed:
        tests_passed += 1
    else:
        tests_failed += 1
    tests_completed += 1

    passed = check_equal(set(T082_M1_load_data("student-mat.csv",
                                               "health").get("GP")[0].keys()),
                         {"School", "Age", "StudyTime", 'Failures',
                          'Absences', 'G1', 'G2', 'G3'})

    if passed:
        tests_passed += 1
    else:
        tests_failed += 1
    tests_completed += 1

    passed = check_equal(set(T082_M1_load_data("student-mat.csv",
                                               "school").get("GP")[0].keys()),
                         {"Age", "StudyTime", 'Failures', 'Health',
                          'Absences', 'G1', 'G2', 'G3'})

    if passed:
        tests_passed += 1
    else:
        tests_failed += 1
    tests_completed += 1

    passed = check_equal("School Student Keys", set(load_data("student-mat.csv", "age").get(
        "GP")[0].keys()), {'School', 'StudyTime', 'Failures', 'Health', 'Absences', 'G1', 'G2', 'G3'})

    if passed:
        tests_passed += 1
    else:
        tests_failed += 1
    tests_completed += 1

    print(tests_completed)
    
