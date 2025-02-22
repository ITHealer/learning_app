# Learning App

## Overview

This is a simple app that allows you to learn new things.

## Tech Stack

- Next.js
- Tailwind CSS
- TypeScript
- Shadcn UI

## Features

- Login with Google
- Create a new course
- Add new lessons to a course
- Add new questions to a lesson
- Add new answers to a question 

## Step by step guide

### 1. Set up the project
- npx create-next-app@latest <name_project> --typescript --tailwind --eslint

### 2. Install dependencies
- npm install @tanstack/react-query axios @headlessui/react lucide-react next-auth

    + @tanstack/react-query -> for data fetching
       * Quản lý state và cache cho API calls
       * Tự động refetch khi data thay đổi
       * Xử lý loading và error state
       * Giảm số lượng request không cần thiết
       * Cache data ở client side
       ```
       // Ví dụ sử dụng react-query
        import { useQuery } from '@tanstack/react-query';

        function UserProfile() {
        const { data, isLoading } = useQuery({
            queryKey: ['user', userId],
            queryFn: () => fetchUserData(userId)
        });

        if (isLoading) return <div>Loading...</div>;
        return <div>{data.name}</div>;
        }
       ```
    + axios -> for api calls
       * Thư viện để gọi HTTP requests
       * Xử lý errors tốt hơn fetch API
       * Tự động transform data
       * Hỗ trợ cancel requests
      ```
      // Ví dụ sử dụng axios
      import axios from 'axios';

      // Tạo instance để gọi API
      const api = axios.create({
      baseURL: 'https://api.example.com',
      timeout: 5000,
      headers: {
         'Content-Type': 'application/json'
      }
      });

      // Sử dụng để gọi API
      async function getPosts() {
      const response = await api.get('/posts');
      return response.data;
      }
      ```
    + @headlessui/react -> for ui
    + lucide-react -> for icons
    + next-auth -> for authentication


