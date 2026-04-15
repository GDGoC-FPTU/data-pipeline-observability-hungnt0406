[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=23573988&assignment_repo_type=AssignmentRepo)
# Day 10 Lab: Data Pipeline & Data Observability

**Student ID:** AI20K-2A202600429
**Name:** Tran Ngoc Hung

---

## Mo ta

Bai lab nay xay dung mot ETL (Extract - Transform - Load) pipeline tu dong de xu ly du lieu san pham tu file JSON. Pipeline thuc hien cac buoc: doc du lieu, kiem tra chat luong (loai bo gia am va category rong), ap dung business logic (giam gia 10%, chuan hoa category), va luu ket qua ra file CSV. Ngoai ra, bai lab con bao gom thi nghiem stress test so sanh hieu suat cua AI Agent khi su dung du lieu sach va du lieu rac.

---

## Cach chay (How to Run)

### Prerequisites
```bash
pip install pandas pytest
```

### Chay ETL Pipeline
```bash
python solution.py
```

### Chay Agent Simulation (Stress Test)
```bash
# Tao garbage data
python generate_garbage.py

# Chay agent voi ca clean va garbage data
python agent_simulation.py
```

### Chay Autograder Tests
```bash
pytest tests/test_autograder.py -v
```

---

## Cau truc thu muc

```
├── solution.py              # ETL Pipeline script
├── processed_data.csv       # Output cua pipeline (3 records)
├── raw_data.json            # Du lieu dau vao (5 records)
├── generate_garbage.py      # Script tao du lieu rac
├── garbage_data.csv         # Du lieu rac de stress test
├── agent_simulation.py      # Script mo phong AI Agent
├── experiment_report.md     # Bao cao thi nghiem
├── tests/                   # Thu muc chua autograder tests
└── README.md                # File nay
```

---

## Ket qua

- **Tong records dau vao:** 5
- **Records hop le sau validation:** 3 (loai bo 2 records: 1 gia am, 1 category rong)
- **Cot output:** id, product, price, category, discounted_price, processed_at
- **Stress test:** Agent tra loi chinh xac voi clean data (Laptop - $1200), nhung sai hoan toan voi garbage data (Nuclear Reactor - $999999)
