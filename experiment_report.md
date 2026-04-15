# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** AI20K-2A202600429
**Name:** Tran Ngoc Hung
**Date:** 2026-04-15

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu va ghi lai ket qua:

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | Agent: Based on my data, the best choice is Laptop at $1200. | 9 | Correct answer with valid price from clean pipeline output |
| Garbage Data (`garbage_data.csv`) | Agent: Based on my data, the best choice is Nuclear Reactor at $999999. | 1 | Completely wrong due to extreme outlier in poisoned data |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

Khi su dung garbage data, Agent da tra loi sai hoan toan vi du lieu dau vao chua nhieu van de nghiem trong ve chat luong. Dau tien, du lieu co duplicate IDs (id=1 xuat hien hai lan voi hai san pham khac nhau), khien Agent khong the xac dinh chinh xac san pham nao la dung. Thu hai, co mot gia tri outlier cuc ky lon la Nuclear Reactor voi gia $999999 — day la gia tri bat thuong khong phan anh thuc te, nhung vi Agent chi don gian tim gia tri price cao nhat nen no da chon san pham nay. Thu ba, du lieu chua wrong data types nhu "ten dollars" thay vi so, khien cac phep tinh tren cot price co the bi loi. Cuoi cung, cac gia tri null (None) o ca cot id va category gay ra loi khi Agent co gang loc du lieu theo category. Tat ca nhung van de nay chung minh rang neu khong co buoc validation va data cleaning truoc khi dua du lieu vao he thong AI, ket qua se hoan toan khong dang tin cay.

---

## 3. Ket luan

**Quality Data > Quality Prompt?** Dong y. Du cho prompt co tot den dau, neu du lieu dau vao bi "nhiem doc" (duplicates, outliers, null values, wrong types), Agent se cho ra ket qua sai lech. Trong thi nghiem nay, cung mot cau hoi nhung voi du lieu sach thi Agent tra loi chinh xac (Laptop - $1200), con voi du lieu rac thi Agent chon Nuclear Reactor gia $999999. Dieu nay cho thay data quality la nen tang quan trong nhat trong bat ky he thong AI nao.
