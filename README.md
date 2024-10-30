#Source code:

def main(input_param, options):
    a = input_param["firstName"]
    b = input_param["middleName"]
    c = input_param["lastName"]
    d = a + b + c
    return Response.Success({"fullName": d});

    e = input_param["D.O.B"]
    f = input_param["age"]
    g = input_param["identityMark"]
    return Response.Success({"identification": f"Born in {e}, and I'm {f} years old and I have {g}."})

    h = input_param["fromCity"]
    i = input_param["distt."]
    j = input_param["state"]
    return Response.Success({"address": f"from {h}, distt. {i}, {j}"})

    k = input_param["fatherName"]
    l = input_param["motherName"]
    return Response.Success({"parents": f"son of Mr. {k} and Mrs. {l}"})

    m = input_param["occupation"]
    n = input_param["collegeName"]
    o = input_param["city"]
    return Response.Success({"work": f"I am {m} at {n}, {o}"})

    p = input_param["course"]
    q = input_param["school"]
    r = input_param["specialization"]
    return Response.Success({"education": f"course of {p}, school of {q}, with specialization in {r}"})

    u = input_param["internAt"]
    return Response.Success({"internship": f"intern at {u}"})

    v = input_param["hobby"]
    w = input_param["favouriteColour"]
    x = input_param["favouriteFood"]
    y = input_param["favouriteBook"]
    z = input_param["favouritePlace"]
    return Response.Success({
                                "interests": f"hobby is {v}, favouriteColour is {w}, favouriteFood is {x}, favouriteBook is {y}, favouritePlace is {z}"})

    ab = input_param["friend1"]
    bc = input_param["friend2"]
    cd = input_param["friend3"]
    return Response.Success({"friends": f"my friends are {ab}, {bc}, {cd}"})

    de = input_param["achievement1"]
    ef = input_param["achievement2"]
    fg = input_param["achievement3"]
    return Response.Success({"achievements": f"my achievements are {de}, {ef}, {fg}"})

    return Response.Error('ERLX002', 'ErrorMessage', 'ErrorDetails');
