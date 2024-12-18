# �������� ������� ���������

## ����� `Model`

### ������
| ����                         | ��������                                                                 |
|------------------------------|--------------------------------------------------------------------------|
| `virtual double simulate(double prevOutput, double input, double prevInput) = 0` | ����������� ����� ��� ��������� ������ ������.                          |
| `virtual ~Model() = default` | ���������� ��� ����������� ������� `Model`.                             |

### ��������
����� `Model` �������� ����������� �������, ������� ������ ��������� ��� ���� �������. ����� `simulate` ������ ���� ���������� � ����������� �������.

---

## ����� `LinearModel`

### ������
| ����                         | ��������                                                                 |
|------------------------------|--------------------------------------------------------------------------|
| `public inline LinearModel(double a, double b)` | ����������� ��� �������� ������ ������� `LinearModel`.                   |
| `public inline virtual double simulate(double prevOutput, double input, double prevInput)` | ���������������� ����� ��� ������� ��������� ��������.                   |
| `public virtual ~LinearModel() = default` | ���������� ��� ����������� ������� `LinearModel`.                       |
| `private double a`           | �������� `a`.                                                           |
| `private double b`           | �������� `b`.                                                           |

### ��������
����� `LinearModel` ������������ ����� �������� ������ ����������, ������������ �������� ���������� ����������� ������ � �������� ����� ��� ���������� ������ ������.

---

## ����� `NonlinearModel`

### ������
| ����                         | ��������                                                                 |
|------------------------------|--------------------------------------------------------------------------|
| `public inline NonlinearModel(double a, double b, double c, double d)` | ����������� ��� �������� ������ ������� `NonlinearModel`.               |
| `public inline virtual double simulate(double prevOutput, double input, double prevInput)` | ���������������� ����� ��� ������� ��������� ��������.                   |
| `public virtual ~NonlinearModel() = default` | ���������� ��� ����������� ������� `NonlinearModel`.                   |
| `private double a`           | �������� `a`.                                                           |
| `private double b`           | �������� `b`.                                                           |
| `private double c`           | �������� `c`.                                                           |
| `private double d`           | �������� `d`.                                                           |
| `private double prevOutput`   | ���������� �������� ������.                                             |
| `private double prevInput`    | ���������� �������� �����.                                             |

### ��������
����� `NonlinearModel` ��������� ���������� ������ ����������, ����������� ������������ � �������������� ����������� ��� ���������� ������.

---

## ����� `PIDController`

### ������
| ����                         | ��������                                                                 |
|------------------------------|--------------------------------------------------------------------------|
| `public inline PIDController(double Kp, double Ki, double Kd)` | ����������� ��� �������� ������ ������� `PIDController`.                |
| `public double compute(double setpoint, double measured)` | ����� ��� ���������� ������������ �����������.                          |
| `public virtual ~PIDController() = default` | ���������� ��� ����������� ������� `PIDController`.                    |

### ��������
����� `PIDController` ��������� ���-��������� ��� ���������� ������������ ����������� �� ������ �������� � ���������� ��������.

---

## ����� `Simulation`

### ������
| ����                         | ��������                                                                 |
|------------------------------|--------------------------------------------------------------------------|
| `public inline Simulation(Model& model, PIDController& controller)` | ����������� ��� �������� ������ ������� `Simulation`.                   |
| `public void run(int timeSteps, double setpoint)` | ����� ��� ���������� ���������.                                         |

### ��������
����� `Simulation` �������� �� ���������� ���������, ��������� ������ � ���������� ��� ���������� �������� �������� � ������ ����������� �� �����.

---

## ����������

��� ������ ���������� ������ ���������, ����������� ������ ���������� � ���������. ��� ��������� ������������ ��������� ������ � ������������ ��������� �������� � ���������� � ��������.