# 马克思主义基本原理题库系统

这是一个静态网站版本，入口文件是 `index.html`，可发布到 GitHub Pages。

## GitHub Pages 发布

1. 打开仓库 `https://github.com/vsjsjxh/makesi`
2. 点击 `Add file` -> `Upload files`
3. 上传本文件夹里的全部文件，不要只上传 zip
4. 提交到 `main` 分支
5. 进入 `Settings` -> `Pages`
6. `Source` 选择 `Deploy from a branch`
7. `Branch` 选择 `main`，目录选择 `/root`
8. 保存后等待 1 到 5 分钟

发布地址应为：

`https://vsjsjxh.github.io/makesi/`

## 搜索引擎

上线后可以把 `sitemap.xml` 提交到 Google Search Console 或百度搜索资源平台。收录通常需要几天到几周。

## 云端保存

GitHub Pages 是静态网站，不能直接把答题记录写回仓库或服务器。页面内置两种云端保存方式：

- Supabase：填写 Project URL、anon public key 和表名。
- 通用 POST 接口：填写一个能接收 JSON 的 HTTPS API 地址。

Supabase 表可以按下面字段创建：

```sql
create table exam_attempts (
  record_id text primary key,
  learner_id text not null,
  learner_name text,
  score int,
  correct int,
  total int,
  time_spent int,
  paper_seed text,
  question_ids jsonb,
  details jsonb,
  created_at timestamptz
);
```
